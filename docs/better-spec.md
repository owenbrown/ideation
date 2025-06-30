# Better spec2
Product specs are overwhelming for engineers.

## Current process
- Product managers find a need for a new feature.
- Product managers select the requirements of the feature. Sometimes an engineer is involved, but often the product manager has sufficient information about the system to completely specify what the feature should do.
- Product managers give the spec docs to a UX person who mocks out the feature, or the product manager does it himself. The doc lives in a mockup tool like InDesign, Sketch, or Invision.
- Product managers create long technical requirements documents in Google Docs.
  - If done properly, the document has headings so that Google Docs creates a table-of-contents pane.
- There is usually a kickoff meeting.
- Engineers reads the spec and asks questions in the meeting or through comments in the doc.
- Assuming the product is a website or web app, the next step is to determine what engineering needs to do on the front and back end.
- The backend and frontend engineer then come point-by-point through the product spec, determining what data is needed for the front end to do its job, and which backend API endpoints will serve that data.
- The front and backend are smart if they create two or three separate documents. The first document maps the product features to a API endpoints. The second document records each of the relevant API endpoints current and future structures. If this document doesn't exist, then when the front end team begin developement, they are ofter surprised that the fields returned by the API endpoint don't contain exactly what they need. A final document should describe any migrations, which are change to the underlying data structure, and any changes to how data is processed outside of the APIs endpoints already listed.
- Often, backend begins work before frontend. This is because total velocity for the frontend team is higher if they are working with live API endpoints, rather than mock API responses. If the spec is done correctly, however, the cost of switching from mock API responses to real responess is reduced.
- If the product spec changes, then both engineers should review each of the parts of the spec that changed, and carefully decide whether additional information is required from the existing API endpoints, or if new API endpoints are required.

## Pain points
1. The inital document is overwhelmingly long, and there is now way to hide or colloapse sections to make it less overwhelming.
2. Product usually doesn't deep-link each part of the product spec to the relevant pages in the mockup. This would save developers time.
3. Copying the request-and-response of each API endpoint feels like busywork. Djange Rest Framework and other API frameworks automatically generate docs, but teams don't use them. (Thinking through this, ideally, when the team creates their API planning doc, they would deep-link to the docs automatically created by Django Rest Framework).
4. Even if recording the existing API docs was easy, mocking up the proposed request-and-response format is still a pain. What the backend engineer wants to see is a _diff_ between the current request and response framework, and what is required.
5. If the engineer were to add a link from every feature bullet-point to the API that would provide the data for that feature, then the requirements document would become unreadable.

## Ideas
- Perhaps the product spec processed could be improved with a better tool for creating tech specs, mapping them to API endpoints, and doing it all in a way that focuses an _information hiding_. That is, create clean views of the spec that hide what is irrelevant in different contexts. For example, the product manager and designer don't need to know about the API endpoints that are used to create functionality, so they shouldn't have to see those links. Finally, the ideal tool would make it easy to plan how long it would take to develop each part of the tool, and would map the development to JIRA stories.
