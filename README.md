1. Start the keycloak server with an offset of 100
2. Start the wildfly server
3. Copy the adapter files that are downloaded from keycloak into the wildfly server directory. For this demo, open-id adapters have already been copied.
4. Create a sample realm. For this example, a realm 'demo' has already been configured in keycloak server
5. Create user, under Manage > Users tab.
6. Under Clients tab create a new client. Id : Vanilla, url : http://localhost:8080/vanilla
7. Go to Installation tab, Select Keycloak OIDC JBoss Subsystem XML and copy the xml content there.
8. Open the standalone/configuration/standalone.xml file and search for the following text:
	<subsystem xmlns="urn:jboss:domain:keycloak:1.1"/>
9. Modify this to prepare it for pasting in your template from the Installation page:
	<subsystem xmlns="urn:jboss:domain:keycloak:1.1">
	</subsystem>
10. Within the <subsystem> element, paste in the template that was copied earlier.
11. replace the war name with vanilla.war
12. Reboot application server
13. Go to http://localhost:8080/vanilla and click login. Sample user is demouser@gmail.com
