This is a Spring Boot application using MVC and Rest controllers. The admins' and doctors' dashboards use Thymeleaf templates. The rest is served via REST APIs.
The application uses a MySQL database for the structured data (patients, doctors, admins, appointments) and a MongoDB for the unstructured data (prescriptions).
All controllers route their requests to a common service layer which routes its requests to the corresponding repositories. MySQL datas are mapped to JPA entities while MongoDB datas are mapped to document models.

1. User accesses an Admin or Appointment dashboard page.
2. The request is routed to the corresponding thymeleaf or REST controller
3. The controller calls the service layer and gets the proper model in an appropriate format
4. The service layer calls the repository layer and gets usable java objects from it
5. The repository layer fetches the MongoDB and maps it to a document mode (prescrption) or the MySQL and maps it to a JPA entity (the rest)
6. This data comes back to the controller through the different layers
7. This data is shown to the user either via a thymeleaf webpage either via a REST API
