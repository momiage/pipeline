pipeline{
    agent none
    stages{
        stage('No1.:Windows for print job Slave'){
           agent{
               label 'Slave'
           }
            steps{
                echo 'start'
                dir('Windows') {
                    // some block

                bat 'WindowsCase_1_New.au3'
                 bat '''javac ReadTxtFile.java
                                                                        java ReadTxtFile'''

                }
            }

        }
        stage('No3:Cheetah '){
            agent{
                label 'master'
            }
            steps{
                retry(3){

                sh 'pwd'
                writeFile file: 'autotestinfo1.txt', text: '165.96.211.138:49110'
                //writeFile file: 'autotestinfo1.txt', text: '172.25.76.146:49110'
                writeFile file: 'autotestinfo2.txt', text: '4.2.2'
                writeFile file: 'autotestinfo3.txt', text: 'http://0.0.0.0:4990/wd/hub'

                sh 'sudo ${adbHome}/adb connect 165.96.211.138:49110'
                //sh 'sudo ${adbHome}/adb connect 172.25.76.146:49110'

                sh 'sudo rm -f testng.xml'
                sh 'sudo cp -af testng3chimay.xml testng.xml'
                timeout(5) {
                sh 'sudo ${mvnHome}/mvn test -f pom.xml -DxmlFileName=testng.xml'
                }
                sh '''sudo javac ReadTxtFile.java
                sudo java ReadTxtFile'''

                }

            }

               post {
               always {
                      publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: true, reportDir: 'target/surefire-reports', reportFiles: 'report.html', reportName: 'HTML Report', reportTitles: ''])
                                      //archiveArtifacts artifacts: '**/target/surefire-reports/report.html' , fingerprint:true
                }
                }

        }
        stage('No4:Webpage '){
            agent{
                label 'master'
            }
           steps{
                        retry(3){
                        writeFile file: 'autotestinfo1.txt', text: 'emulator-5554'
                        writeFile file: 'autotestinfo2.txt', text: '6.0'
                        writeFile file: 'autotestinfo3.txt', text: 'http://0.0.0.0:4990/wd/hub'
                        sh 'sudo ${adbHome}/adb connect 165.96.211.138:49110'
                        sh 'sudo ${adbHome}/adb disconnect 165.96.211.138:49110'
                                               // sh 'sudo ${adbHome}/adb connect 172.25.76.146:49110'
                                                //sh 'sudo ${adbHome}/adb disconnect 172.25.76.146:49110'
                        sh 'sudo rm -f testng.xml'
                        sh 'sudo cp -af testng4chimay.xml testng.xml'
                        sh 'sudo ${mvnHome}/mvn test -f pom.xml -DxmlFileName=testng.xml'
                        sh '''sudo javac ReadTxtFile.java
                        sudo java ReadTxtFile'''
                    }
            }

                      post {
                                                always {
                                  publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: true, reportDir: 'target/surefire-reports', reportFiles: 'report.html', reportName: 'HTML Report', reportTitles: ''])
                                                 // archiveArtifacts artifacts: '**/target/surefire-reports/report.html' , fingerprint:true

                                                }
                                                }


        }

    }
}