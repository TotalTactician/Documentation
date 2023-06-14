# Portfolio of Joey
![skaven-cheiften](https://github.com/TotalTactician/Documentation/assets/81526735/3a668864-4463-4775-950d-6764ee7156d6)

Thanks to [Erik Van de Laar](https://github.com/tick-github/tick-documentation) for the inspiration on how to set up this document.

## Table of Contents
- [Intro](#intro)
- [Learning outcomes](#learning-outcomes)
- [Proof](#proof)
- [Self-assessment](#self-assessment)
  - [Web Application](#web-application)
  - [Software Quality](#software-quality)
  - [Agile Methodology](#agile-methodology)
  - [CI/CD](#cicd)
  - [Cultural Differences and Ethics](#cultural-differences-and-ethics)
  - [Requirements and Design](#requirements-and-design)
  - [Business Processes](#business-processes)
  - [Professional](#professional)

## Intro
Within this document, I aim to present the learning outcomes specific to the current semester as of June 1st, 2023. 
I collaborated on this project with [Sylvester Snijders](https://github.com/AsterosTheGreat), and you will find a table in this document containing explanations of these outcomes, along with comprehensive evidence of my work that demonstrates my successful attainment of each outcome.

## Learning outcomes
For a complete list of the learning outcomes and their explanation as of June 1, 2023, see [here](https://github.com/TotalTactician/Documentation/blob/main/learning-outcomes.md).

## Proof
| explanation                     | Learing outcome                                                                           | Proof                                                                                        |                                   
|---------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------|
| The structure of our TotalTactitian application and explaining some choices | [Web Application ](https://github.com/TotalTactician/Documentation/blob/main/learning-outcomes.md#web-application) | [🔗](https://github.com/TotalTactician/Documentation/blob/main/Proof/Joey/Web%20Application.md) |
| Unit tests in NodeJS microservice | [Software Quality](https://github.com/TotalTactician/Documentation/blob/main/learning-outcomes.md#web-application) | [🔗](https://github.com/TotalTactician/Documentation/blob/main/Proof/Joey/Software%20Quality.md) |
| What is agile and how did we use it in the group project | [Agile Methodology](https://github.com/TotalTactician/Documentation/blob/main/learning-outcomes.md#agile-methodology) | [🔗](https://github.com/TotalTactician/Documentation/blob/main/Proof/Joey/Agile%20Methodology.md) |
| A implementation of CI on a Nodejs microservice with deployment to Dockerhub | [CI/CD](https://github.com/TotalTactician/Documentation/blob/main/learning-outcomes.md#cicd) | [🔗](https://github.com/TotalTactician/Documentation/blob/main/Proof/Joey/CI-CD.md) |
| A document of how we incorporated ethics into our project and what we noticed about cultural differences in the group | [Cultural Differences and Ethics](https://github.com/TotalTactician/Documentation/blob/main/learning-outcomes.md#cultural-differences-and-ethics) | [🔗](https://github.com/TotalTactician/Documentation/blob/main/Proof/Joey/Cultural%20Differences%20and%20Ethics.md) |
| A short document about our design choices | [Requirements and Design](https://github.com/TotalTactician/Documentation/blob/main/learning-outcomes.md#requirements-and-design) | [🔗](https://github.com/TotalTactician/Documentation/blob/main/Proof/Joey/Requirements%20and%20Design.md) |
| A document on the business processes of our own and the group project | [Business Processes](https://github.com/TotalTactician/Documentation/blob/main/learning-outcomes.md#business-processes) | [🔗](https://github.com/TotalTactician/Documentation/blob/main/Proof/Joey/Business%20Processes.md) |
| small text on professionalism | [Professional](https://github.com/TotalTactician/Documentation/blob/main/learning-outcomes.md#professional) | [Professional](#professional) |

# Self-assessment

Below, I will provide the reader with a self-assessment. In this assessment, I will assess my own qualities, and explain how I think I qualify for the given learning outcome (as they are laid out [here](https://github.com/TotalTactician/Documentation/blob/main/learning-outcomes.md)). 

The proficiency ratings I will give myself are as they are described on [CANVAS](https://fhict.instructure.com/courses/12993/outcomes) on June 9th, 2023. The rating goes from '*Undefined*', to '*Orienting*', to '*Beginning*', '*Proficient*', and finally to '*Advanced*', on a scale of 0 to 5.

## Web Application

<table>
  <tr>
    <th><strong>Learning Outcome</strong></th>
    <td>"You design and build user-friendly, full-stack web applications."</td>
  </tr>
  <tr>
    <th><strong>Proficiency Rating</strong></th>
    <td> Proficient </td>
  </tr>
  <tr>
    <th><strong>Explanation</strong></th>
    <td>
      <p>
        I  designed and developed a full-stack application, utilizing a Svelte frontend and primarily implementing microservices in TypeScript with Express.
      </p>
      <p>
        The Race Microservice is responsible for reading from and writing to a MongoDB document store using Mongoose, an ORM for MongoDB. The data is stored in a MongoDB Docker container.
      </p>
    </td>
  </tr>
</table>

## Software Quality

<table>
  <tr>
    <th><strong>Learning Outcome</strong></th>
    <td>"You use software tooling and methodology that continuously monitors and improve the software quality during software development."</td>
  </tr>
  <tr>
    <th><strong>Proficiency Rating</strong></th>
    <td> Proficient </td>
  </tr>
  <tr>
    <th><strong>Explanation</strong></th>
    <td>
      <p>
        I have conducted tests on various microservices that require testing, employing mocking techniques to isolate the tests and ensure their reproducibility.
      </p>
      <p>
        Before merging any code, it must successfully pass all tests and receive approval from another developer in the team through peer reviews. 
        This holds true for both personal projects and group projects alike.
      </p>
      <p>
        In our group project, it would have been advantageous to prioritize testing more prominently. Unfortunately, we initiated the testing process a bit later than ideal.
      </p>
    </td>
  </tr>
</table>

## Agile Methodology

<table>
  <tr>
    <th><strong>Learning Outcome</strong></th>
    <td>"You choose and implement the most suitable agile software development method for your software project."</td>
  </tr>
  <tr>
    <th><strong>Proficiency Rating</strong></th>
    <td> Proficient </td>
  </tr>
  <tr>
    <th><strong>Explanation</strong></th>
    <td>
      <p>
        During every sprint, we conducted a sprint planning session to determine the tasks to be accomplished in the upcoming sprint. Additionally, at the end of each sprint, we held a retrospective to reflect upon the previous sprint.
      </p>
      <p>
        We utilized tools like Jira to document user stories and manage our sprint board efficiently.
      </p>
      <p>
        We conducted a form of refinement process to ensure that user stories were thoroughly developed. However, there is room for improvement in this aspect.
      </p>
      <p>
        As part of our assignment, we were tasked with outsourcing a user story to another student and, in return, implementing a user story from a different student. See <a href="https://github.com/TotalTactician/Documentation/blob/main/Proof/Joey/Agile%20Methodology.md#outsourcing">here</a>
      </p>
    </td>
  </tr>
</table>

## CI/CD

<table>
<tr>
  <th><strong>Learning Outcome</strong></th>
  <td>"You design and implement a (semi)automated software release process that matches the needs of the project context."</td>
</tr>
<tr>
  <th><strong>Proficiency Rating</strong></th>
  <td> Proficient </td>
</tr>
<tr>
  <th><strong>Explanation</strong></th>
  <td>     
    <p>
      I possess the knowledge and skills to establish CI/CD workflows within GitHub, ensuring their activation whenever applicable.
    </p>
  </td>
</tr>
</table>

## Cultural Differences and Ethics

<table>
  <tr>
    <th><strong>Learning Outcome</strong></th>
    <td>"You recognize and take into account cultural differences between project stakeholders and ethical aspects in software development."</td>
  </tr>
  <tr>
    <th><strong>Proficiency Rating</strong></th>
    <td> Proficient </td>
  </tr>
  <tr>
    <th><strong>Explanation</strong></th>
    <td>
        <p>
          See <a href="https://github.com/TotalTactician/Documentation/blob/main/Proof/Joey/Cultural%20Differences%20and%20Ethics.md">here</a>.
        </p>
    </td>
  </tr>
</table>

## Requirements and Design

<table>
  <tr>
    <th><strong>Learning Outcome</strong></th>
    <td>"You analyze (non-functional) requirements, elaborate (architectural) designs and validate them using multiple types of test techniques."</td>
  </tr>
  <tr>
    <th><strong>Proficiency Rating</strong></th>
    <td> Proficient </td>
  </tr>
  <tr>
    <th><strong>Explanation</strong></th>
    <td>
        <p>
          Prior to commencing the project, we documented our program's intended objectives and the problem we aimed to address. 
          Based on this information, we created a C4 diagram to visualize the system's architecture and components.
          C4 can be found <a href="https://github.com/TotalTactician/Documentation/blob/main/Proof/Joey/Web%20Application.md#application-structure">here</a>.
        </p>
    </td>
  </tr>
</table>

## Business Processes

<table>
  <tr>
    <th><strong>Learning Outcome</strong></th>
    <td>"You analyze and describe simple business processes that are related to your project."</td>
  </tr>
  <tr>
    <th><strong>Proficiency Rating</strong></th>
    <td> Proficient </td>
  </tr>
  <tr>
    <th><strong>Explanation</strong></th>
    <td>
        <p>
          See  <a href="https://github.com/TotalTactician/Documentation/blob/main/Proof/Joey/Business%20Processes.md">here</a> and  <a href="https://github.com/Null-Not-Found/DashBuddy-Documentation/blob/main/Learning%20Outcomes/Business%20processes.md">here</a>.
        </p>
    </td>
  </tr>
</table>

## Professional

<table>
  <tr>
    <th><strong>Learning Outcome</strong></th>
    <td>"You act in a professional manner during software development and learning."</td>
  </tr>
  <tr>
    <th><strong>Proficiency Rating</strong></th>
    <td> Proficient </td>
  </tr>
  <tr>
    <th><strong>Explanation</strong></th>
    <td>
      <p>
        I maintained a regular practice of seeking feedback from the teacher, typically at intervals of at least once every two weeks. This feedback was shared on Feedpulse, serving as a significant milestone to update           the teacher about my progress and experiences. 
        It served as an opportunity to demonstrate my proficiency and convince them of my readiness to proceed to the next semester.
      </p>
      <p>
        In the group project, I assumed the role of the contact person, responsible for addressing any uncertainties or feedback needs within the group. Additionally, I took charge of organizing the retrospectives to ensure a systematic evaluation of our project progress. For more, see <a href="https://github.com/TotalTactician/Documentation/blob/main/Proof/Joey/Agile%20Methodology.md#retrospectives">here</a>
      </p>
    </td>
  </tr>
</table>
