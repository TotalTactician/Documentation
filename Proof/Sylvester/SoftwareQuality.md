# Software Quality Proof

## Table of Contents
- [Intro](#intro)
- [pytest Integration Test](#pytest-integration-test)
- [Playwright Snapshot Test](#)

## Intro
During the semester we have had to keep an eye on the quality of our software. For this I made some tests in the different parts of the project I worked on.

## pytest Integration Test
In the [Unit Management](https://github.com/TotalTactician/TOT_UnitManagement) microservice I utilized pytest to test the endpoint. Due to the small size of the microservice and there not being any significant code to test I didnt use unit tests. Instead I tested if the api returned what it should return if given an ID. For this I mocked the function of the ODM to ensure it only tests the code in the microservice and not the database or its connection.

```python
def test_getUnit(app, mocker):

    # Define a sample unit
    sample_unit = {"_id": ObjectId("647f10601bf12007cc8b55c6"), "name": "Test Unit"}
    mocker.patch.object(app.db, "find_one", return_value=sample_unit)

    # Make a request to the API endpoint
    response = app.test_client().get(f"/api/unit/{sample_unit['_id']}")

    # Check that the response status code is 200
    assert response.status_code == 200

    # Check that the response data matches the sample unit
    print(response.data)
    assert json.loads(response.data) == json.loads(json.dumps(sample_unit, default=str))

```
## Playwright Snapshot Test
In the frontend I used a snapshot test on the mainpage to ensure that only wanted changes make it trough. If something on the page is changed due to external sources (Bug, layout change etc.) I have to go and look at the page and approve the changes by making a new snapshot.

```ts
test('snapshot test', async ({ page }) => {
	await page.goto('/');
	await expect(page).toHaveScreenshot();
});
```
