## 🧐 About <a name = "about"></a>

Fast Healthcare Interoperability Resources (FHIR) revolutionizes data exchange in healthcare, enhancing interoperability across systems. Developed by HL7, FHIR employs web technologies for seamless communication in hospitals like GOSH, aggregating data for unified patient records. It promotes interoperability among EHR systems, streamlining data access, improving care coordination, and enabling patient engagement. The UCL FHIRWorks 2024 emphasizes leveraging FHIR for innovative healthcare solutions, providing students with a platform to apply programming skills for enhanced patient care and healthcare informatics transformation.

## 🔥 Getting Started <a name = "getting_started"></a>

To get started building and coding SMART-on-FHIR applications, you'll need a combination of foundational knowledge, tools, and resources. Here are the basic things required to begin coding SMART-on-FHIR applications.

### Prerequisites

1. Understanding of FHIR Standards:
Familiarize yourself with the Fast Healthcare Interoperability Resources (FHIR) standard using the [FHIR Documentation](https://fhir-ru.github.io/documentation.html). However, a good knowledge of [FHIR resources RESTful APIs, searching and the principles](https://fhir-ru.github.io/search.html) of data exchange in healthcare is important.

2. Knowledge of OAuth 2.0:
[SMART-on-FHIR](https://docs.smarthealthit.org/client-js/) uses OAuth 2.0 for authorization. Gain a solid understanding of OAuth 2.0 for authentication and authorization in healthcare applications.

3. Development Environment:
Set up a development environment with a suitable programming language (e.g., JavaScript, Python, Java) and a web development framework.

4. FHIR Server:
Choose or set up a FHIR server to interact with FHIR resources. You can use public servers like [HAPI FHIR](http://hapi.fhir.org/baseR4), or [set up your own](https://github.com/gosh-dre/ucl-fhir-hack/blob/master/docker-compose.yml). In our case, we are going to use [Azure API for FHIR](https://learn.microsoft.com/en-us/azure/healthcare-apis/fhir/) provided by GOSH.

5. SMART-on-FHIR Client Library:
Utilize a SMART-on-FHIR client libraries -- [Javascript](https://docs.smarthealthit.org/client-js/) or [Python](https://docs.smarthealthit.org/client-py/) in your chosen programming language. These libraries simplify the process of working with SMART-on-FHIR specifications. Explore real-world [use cases and examples](https://docs.smarthealthit.org/tutorials/server-quick-start/#) of SMART-on-FHIR applications. Understanding how SMART-on-FHIR is applied in practical scenarios can guide your development.

6. Testing Environment:
Access a [testing environment](https://smarthealthit.org/developer-resources/) with sample patient data. Platforms like the [SMART Health IT Sandbox](https://docs.smarthealthit.org/) provide a simulated environment for testing SMART-on-FHIR applications.

7. Community Support:
Join forums, communities, or discussion groups related to [SMART Health IT and FHIR development](https://smarthealthit.org/smart-on-fhir-community/). Engage with the community to seek guidance, share experiences, and stay updated on best practices.

### Setting up your App development

Now that you have a good understanding of FHIR API, Smart-on-fhir applications, design and implementations, you are ready to use the GOSH FHIR server for the Hackathon. We've provided [example setup](https://github.com/gosh-dre/ucl-fhir-hack) using [Vue JS](https://vuejs.org/). This template shows you how to run example SMART-on-FHIR App developed for testing the Hack. However, you can use other `javascript` frameworks such as [`ReactJS`](https://legacy.reactjs.org/docs/getting-started.html), [`svelte`](https://www.npmjs.com/package/svelte), [`AngularJS`](https://docs.angularjs.org/guide), etc

If you are using [Javascript](https://docs.smarthealthit.org/client-js/), which is required for frontend development, these frameworks are required to be installed.

1. [Node JS](https://nodejs.org/en/download/package-manager)
2. [Javascript](https://docs.smarthealthit.org/client-js/) client

However, if you prefer `Python`, these frameworks are required to be installed:

1. [Python 3.x](https://www.python.org/downloads/)
2. [fhirclient](https://pypi.org/project/fhirclient/) client with example setup.
3. [fhirpy](https://pypi.org/project/fhirpy/#conditional-update) for fhir data manipulation.

##
⭐️ **tips** Developers can use [`Vanya Client`](https://vanyalabs.com/Integrations/Azure) to view and validate created `FHIR` resources.

##
If for any reason you would want to continue developing on your own within your local FHIR server, you'd need to install the following:

1. [Docker](https://docs.docker.com/engine/install/)
2. [Postgres](https://commandprompt.com/education/how-to-download-and-install-postgresql/)
3. Download the fhir data from [Synthea](https://mitre.box.com/shared/static/ydmcj2kpwzoyt6zndx4yfz163hfvyhd0.zip)
4. Load the downloaded data to the `URL`, which can be found at `http://localhost:8090/fhir` by using the [Python code](https://rajvansia.com/synthea-hapi-fhir.html) as shown.

## Running the FHIR Server locally

To run the FHIR Server locally, install the necessary frameworks as specified above, create a `docker-compose.yml` file in your preferred directory location, copy and paste [docker file](https://github.com/gosh-dre/ucl-fhir-hack/blob/master/docker-compose.yml) into a `.yml` file. Then run `docker-compose up` to start the server. This will run the server locally.

After you must have created and run the docker file, go to your browser and run `http://localhost:8090/fhir/metadata` to show you the server capabilities -- what the server can do.

**Please Note** You can use [Postman](https://learn.microsoft.com/en-us/azure/healthcare-apis/fhir/use-postman) or any other API platform to access your server for testing purposes.

##
### Building mobile-based FHIR Application.

We are yet to register the GOSH FHIR API with Apple for iOS / Android App developers. Hence, the Hackathon will not support development of smart-on-fhir App for mobile application. However, based on the learnings on this Hack, students are adviced to develope apps using [`swift-smart`](https://docs.smarthealthit.org/Swift-SMART/) documentation. 

##
### Project submission 

* [How to submit your projects](#how-to-submit-your-projects)




