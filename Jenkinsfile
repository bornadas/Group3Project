pipeline {
    environment {
            PATH = "C:\\WINDOWS\\SYSTEM32;C:\\Tools\\Java\\jdk-17.0.1\\bin"
    }
    agent {   label 'Grupp3JMeter'   }
    
    stages{
        stage('Run Jmeter tests') {
            steps {
                bat 'C:\\Tools\\apache-jmeter-5.4.1\\bin\\jmeter.bat -Jjmeter.save.saveservice.output_format=xml -n -t C:\\Tools\\apache-jmeter-5.4.1\\bin\\PerformanceTest\\TestPlanGroup3Project.jmx -l jmeter_report.jtl'
                perfReport 'jmeter_report.jtl'
            }
        }
    }
    post {
        success {
            junit 'target/surefire-reports/**/*.xml'                       
        }
    }
}