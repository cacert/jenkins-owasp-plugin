pipeline{
    agent any

        tools {
            maven 'maven_3_5_0'
        }

    stages{
        stage('deneme'){

            steps{
                sh 'mvn clean test'
            }
        }
        stage('package'){

                    steps{
                        sh 'mvn package'
                    }
                }
        stage ('OWASP Dependency Check'){
            steps {

                dependencyCheckAnalyzer datadir: '', hintsFile: '', includeCsvReports: false, includeHtmlReports: false, includeJsonReports: false, isAutoupdateDisabled: false, outdir: '', scanpath: '${WORKSPACE}', skipOnScmChange: false, skipOnUpstreamChange: false, suppressionFile: '', zipExtensions: '',includeVulnReports: false
                dependencyCheckPublisher canComputeNew: false, defaultEncoding: '', healthy: '85', pattern: '**/dependency-check-report.xml', shouldDetectModules: true, unHealthy: ''

           }
        }
    }
}