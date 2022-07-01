pipeline {
    agent any	
    stages {
        stage('Test') {
            steps {
                dir('/Users/loantran/Downloads/BrowserStackScript'){
                    sh 'docker run -t --rm -v "$(pwd)":/tmp/project katalonstudio/katalon katalonc.sh -projectPath=/tmp/project -browserType="Chrome" -retry=0 -statusDelay=15 -testSuitePath="Test Suites/test maximize windows" -executionProfile="default" -apiKey="ce1504db-a920-429e-92da-894ead237b33"'
                }
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'Reports/**/*.*', fingerprint: true
            junit 'Reports/**/JUnit_Report.xml'
        }
    }
}
