Step 4: Install Suggested Plugins
Follow the on-screen instructions to install the suggested plugins and create your first admin user.

Step 5: Configure JDK and Maven in Jenkins
Open Jenkins Web Interface:

Go to http://localhost:8080.
Manage Jenkins:

Click on Manage Jenkins from the left-hand menu.
Global Tool Configuration:

Click on Global Tool Configuration.
Add JDK
Add JDK:

Scroll down to the JDK section.
Click Add JDK.
Uncheck the box Install automatically if you have JDK already installed and configured on your system.
Name: Provide a name for the JDK installation (e.g., DefaultJDK).
JAVA_HOME: Provide the path to the JDK installation. You can find this path by running echo $JAVA_HOME or manually locating it (usually something like /usr/lib/jvm/java-11-openjdk-amd64).
Example Configuration:

sh
Copy code
Name: DefaultJDK
JAVA_HOME: /usr/lib/jvm/java-11-openjdk-amd64
Add Maven
Add Maven:

Scroll down to the Maven section.
Click Add Maven.
Uncheck the box Install automatically if you have Maven already installed and configured on your system.
Name: Provide a name for the Maven installation (e.g., Maven).
MAVEN_HOME: Provide the path to the Maven installation. You can find this path by running mvn -v and looking at the Maven home directory or manually locating it (usually something like /usr/share/maven).
Example Configuration:

sh
Copy code
Name: Maven
MAVEN_HOME: /usr/share/maven
Save the Configuration:

After adding JDK and Maven, scroll down and click Save.
Step 6: Configure Jenkins Job to Use JDK and Maven
Create a New Pipeline Job:

Go to Dashboard > New Item.
Enter a name for the pipeline job (e.g., JavaCalculatorPipeline) and select Pipeline.
Click OK.
Configure the Pipeline:

In the Pipeline section, select Pipeline script from SCM.
Choose Git and enter the repository URL (if using a remote repository).
If the repository is private, provide the necessary credentials.
Specify the branch to build (e.g., main).
Example Jenkinsfile:

Create a Jenkinsfile in the root of your project repository with the following content: