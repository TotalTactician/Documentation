# Software Quality
# contents
- [Intro](#intro)
- [Microservice test](#microservice-test)

# Intro
Unit testing is a vital tool to provide a clear picture of the functionality of the program, furthermore it is a critical way of verifing the customer's requirments.

For testing the NodeJS backend i used Mocha with chai, with Sinon for mocking.

# Microservice test
for a small microservice it is more important to test the endpoint than every piece of code, Because if the endpoint doesnt do what it must do, it isnt working right.

In the Code below you can see a example of such a test. In this test we specify what we expect, in this case it should return a list of multiple races with 200 status code. Then in the test we first replace the real DAL with the testDAL so we dont use real data (more info below). After that we call the endpoint and first check if it has the right status code, after that we check if it has the right fields. If one of these checks fail, the test will fail.
```ts
  beforeEach(() => {
    sandbox = sinon.createSandbox();
    TestDAL = new TestRaceDAL();
  });

  afterEach(() => {
    sandbox.restore();
  } )
  
  // a test  
  it('should return a list of multiple races with 200 status code', async () => {
    sandbox.stub(RaceDAL.prototype, 'getAllRaces').callsFake(async () => TestDAL.getAllRacesReturnList());
    // Make a request to the /GetAll endpoint
    const res = await chai.request(APP).get('/GetAll');

    // Check the response status code
    expect(res).to.have.status(200);

    // Check the response body
    expect(res.body).to.have.property('Time');
    expect(res.body).to.have.property('Races');
    expect(res.body.Races).to.be.an('array');
  });
```
Before each test it sets up a new mock environment with the new testdal, this is important so the tests dont use a real database and every test starts with a clean slate, And after each test the mock enviroment gets cleaned.
This will insure each test has the same environment everytime and (if setup right) will give the same result after multiple runs.
