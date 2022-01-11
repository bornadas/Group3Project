pipeline {
    environment {
            PATH = "C:\\WINDOWS\\SYSTEM32;C:\\Program Files\\Java\\jdk-17.0.1\\bin"
    }
    agent {   label 'grupp3Jmeter'   }
    
    stages{
        stage('Run Jmeter tests') {
            steps {
                bat 'C:\\Tools\\apache-jmeter-5.4.1\\apache-jmeter-5.4.1\\bin\\jmeter.bat -Jjmeter.save.saveservice.output_format=xml -n -t C:\\Tools\\apache-jmeter-5.4.1\\apache-jmeter-5.4.1\\bin\\TestPlanGroup3Project.jmx -l jmeter_report.jtl'
                perfReport 'jmeter_report.jtl'
            }
        }
    }
    post {
       success {   junit allowEmptyResults: true, testResults: "${WORKSPACE}/test-results/*.xml"                      
        }
    }
}