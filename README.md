<h1>Spring Boot Project</h1>

<h3>Objective</h3>
A standalone web-application used to study Spring Boot that provides a list of API's related to objectives management.

<BR>
<h3>Spring Initializr, Spring Boot CLI and Spring Boot STS</h3>
* https://start.spring.io/<BR> - Spring Starter Project
* https://docs.spring.io/spring-boot/docs/current/reference/html/cli-using-the-cli.html<BR>
* https://spring.io/tools/sts

<BR>
<h3>Configuration</h3>
In order to configure the Spring Boot it is necessary to add into the resource folder the file application.properties and inside of it use the key-values properties related to the configuration. It's possible see the properties via the website: https://docs.spring.io/spring-boot/docs/current/reference/html/common-application-properties.html
  
<BR>
<h3>Spring Data JPA (Java Persistence API)</h3>
Examples of Annotations. E.g.:
* Use of Entities: Annotation @Entity
* Primary Key: Annotation @Id
  
<BR>
Interface for Repository - extends CrudRepository.
public class GoalsRepository extends CrudRepository {} <BR>
Main CRUD Methods: <BR>
* findAll, save (for create and update), delete and findOne.
* It is important to remember about @ManyToOne - @OneToMany - @ManyToMany annotations

<BR>
<h3>Packaging and Running</h3>
In order to generate a runable standalone Jar file application it is necessary to execute the command below:
* mvn clean install -> generates a jar file inside the Target Folder
* execute: java -jar ../../../jarName.jar
* It possible to change jar to war throug the pom.xml file.
<BR>  

<h3>Actuator</h3>
Spring Boot Actuator is a sub-project of Spring Boot. It adds several production grade services to your application<BR>
https://spring.io/guides/gs/actuator-service/<BR>
https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#production-ready<BR>
<BR>
<h3>Test Example</h3>
 
@RunWith(SpringRunner.class)
@SpringBootTest(webEnvironment = WebEnvironment.RANDOM_PORT)
public class RandomPortExampleTests {

	@Autowired
	private TestRestTemplate restTemplate;

	@Test
	public void exampleTest() {
		String body = this.restTemplate.getForObject("/", String.class);
		assertThat(body).isEqualTo("Hello World");
	}
}
