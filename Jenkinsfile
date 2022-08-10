pipeline{
    agent any
    triggers{
		pollSCM('* * * * *')
	}
    stages{
        stage("Compile the source code")	{
            steps	{
		    
            sh "./mvnw compile"
            }
        }
        stage("Test the source code")	{
            steps	{
            sh "./mvnw test"
            }
        }
         stage("Code coverage. Limiting the minimum score for lines coverage to 75%")	{
            steps	{
            sh "./mvnw test jacoco:report"
            publishHTML	(target:	[
				reportDir:	'target/site/jacoco',
				reportFiles:	'index.html',
				reportName:	"Code coverage report"
			])
            sh "./mvnw clean verify"
            
            }
        }
	stage("Package the application")	{
            steps	{
            sh "./mvnw clean package -DskipTests"
            }
        }

	stage("Deploy to the staging")	{
	    steps	{
	    sh	"./mvn spring-boot:run"
	}
	}
    }
}
