## From idea to production – steps to creating and consuming APIs

### Mike Adler

__Summary:__
APIs have been around a long time. Now more than ever we build APIs and consume APIs in all types of applications. This talk will cover some of the well learned lessons of Creating and Consuming APIs that lead to better APIs for consumption and better applications that use APIs.

---

APIs are old; been created for the last 40 years

* use & understand the standards; understand the verbs & http states
* write/read the documentation first
* up front, figure out the stuff that's going to kill you later (scaling concerns, implementation issues, etc)
	* versioning: url, request-header, accepts-header
	* authentication/authorization: use keys w/ registration
	* state: don't keep state between calls
* test api
* instrument code
* build sample programs
* build data factories (for testing)
* automate testing environments, not just tests
* make it public; please build a portal!
	* documentation
	* sample programs & data factories
	* dashboards - how is my API performing
	* support (Community)
* the rest:
	* communicate
	* keep it simple
	* focus on building & using value
