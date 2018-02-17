pipeline{
    agent none
    stages{
        stage('parallel job1 for No.11 with No.16'){
            parallel{
                stage('No11:Windows for print job Slave'){
                    agent{
                        label 'Slave'
                    }
                    steps{
                        echo 'start'
                        dir('Windows') {
                    // some block

                bat 'WindowsCase_11_New.au3'
                bat '''javac ReadTxtFile.java
                                                                        java ReadTxtFile'''
                                  //archiveArtifacts 'C:\\jenkins\\workspace\\Test_No1_No3_No4\\'
                              }
                              }
                }
                stage('No16:KB opetaion'){
                    agent{
                        label 'master'
                    }
                steps{
                          retry(3){
                          writeFile file: 'autotestinfo1.txt', text: '165.96.211.138:49110'
                           //writeFile file: 'autotestinfo1.txt', text: '172.25.76.146:49110'
                          writeFile file: 'autotestinfo2.txt', text: '4.2.2'
                          writeFile file: 'autotestinfo3.txt', text: 'http://0.0.0.0:4990/wd/hub'
                          sh 'sudo ${adbHome}/adb connect 165.96.211.138:49110'
                          //sh 'sudo ${adbHome}/adb connect 172.25.76.146:49110'
                          sh 'sudo rm -f testng.xml'
                          sh 'sudo cp -af testng16chimay.xml testng.xml'
                          sh 'sudo ${mvnHome}/mvn test -f pom.xml -DxmlFileName=testng.xml'
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
            }
        }

        stage('No13:natvie cheetah'){
                    agent{
                        label 'master'
                    }
                    steps{
                retry(3){
                writeFile file: 'autotestinfo1.txt', text: '165.96.211.138:49110'
                //writeFile file: 'autotestinfo1.txt', text: '172.25.76.146:49110'
                writeFile file: 'autotestinfo2.txt', text: '4.2.2'
                writeFile file: 'autotestinfo3.txt', text: 'http://0.0.0.0:4990/wd/hub'
                sh 'sudo ${adbHome}/adb connect 165.96.211.138:49110'
                //sh 'sudo ${adbHome}/adb connect 172.25.76.146:49110'
                sh 'sudo rm -f testng.xml'
                sh 'sudo cp -af testng13chimay.xml testng.xml'
                sh 'sudo ${mvnHome}/mvn test -f pom.xml -DxmlFileName=testng.xml'
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
        stage('No14:webpage'){
                    agent{
                        label 'master'
                    }
                    steps{
                                  retry(3){
                                  writeFile file: 'autotestinfo1.txt', text: 'emulator-5554'
                                  writeFile file: 'autotestinfo2.txt', text: '6.0'
                                  writeFile file: 'autotestinfo3.txt', text: 'http://0.0.0.0:4999/wd/hub'
                                  sh 'sudo ${adbHome}/adb connect 165.96.211.138:49110'
                                  sh 'sudo ${adbHome}/adb disconnect 165.96.211.138:49110'
                                                                    //sh 'sudo ${adbHome}/adb connect 172.25.76.146:49110'
                                                                    //sh 'sudo ${adbHome}/adb disconnect 172.25.76.146:49110'
                                  sh 'sudo rm -f testng.xml'
                                  sh 'sudo cp -af testng14chimay.xml testng.xml'
                                  sh 'sudo ${mvnHome}/mvn test -f pom.xml -DxmlFileName=testng.xml'
                                  sh '''sudo javac ReadTxtFile.java
                                  sudo java ReadTxtFile'''
                                  //publishHTML([allowMissing: false, alwaysLinkToLastBuild: true, keepAll: true, reportDir: 'target/surefire-reports', reportFiles: 'report.html', reportName: 'HTML Report', reportTitles: ''])
                                  //archiveArtifacts artifacts: '**/target/surefire-reports/report.html' , fingerprint: true
                              }
                      }

                                     post {
                                     always {
                                            publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: true, reportDir: 'target/surefire-reports', reportFiles: 'report.html', reportName: 'HTML Report', reportTitles: ''])
                                                                                  //archiveArtifacts artifacts: '**/target/surefire-reports/report.html' , fingerprint:true
                                      }
                                      }
                }

        stage('No17:reset machine webpage'){
                    agent{
                        label 'master'
                    }
                    steps{
                        retry(3){
                        writeFile file: 'autotestinfo1.txt', text: 'emulator-5554'
                        writeFile file: 'autotestinfo2.txt', text: '6.0'
                        writeFile file: 'autotestinfo3.txt', text: 'http://0.0.0.0:4999/wd/hub'
                        sh 'sudo ${adbHome}/adb connect 165.96.211.138:49110'
                        sh 'sudo ${adbHome}/adb disconnect 165.96.211.138:49110'
                                               // sh 'sudo ${adbHome}/adb connect 172.25.76.146:49110'
                                                //sh 'sudo ${adbHome}/adb disconnect 172.25.76.146:49110'
                        sh 'sudo rm -f testng.xml'
                        sh 'sudo cp -af testng17chimay.xml testng.xml'
                        sh 'sudo ${mvnHome}/mvn test -f pom.xml -DxmlFileName=testng.xml'
                        sh '''sudo javac ReadTxtFile.java
                        sudo java ReadTxtFile'''
                        //publishHTML([allowMissing: false, alwaysLinkToLastBuild: true, keepAll: true, reportDir: 'target/surefire-reports', reportFiles: 'report.html', reportName: 'HTML Report', reportTitles: ''])
                        //archiveArtifacts artifacts: '**/target/surefire-reports/report.html' , fingerprint: true
                    }
            }

                           post {
                           always {
                                  publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: true, reportDir: 'target/surefire-reports', reportFiles: 'report.html', reportName: 'HTML Report', reportTitles: ''])
                                                                        //archiveArtifacts artifacts: '**/target/surefire-reports/report.html' , fingerprint:true
                            }
                            }
                }
        stage('No18:powser off machine webpage'){
                    agent{
                        label 'master'
                    }
                    steps{
                        retry(3){
                        writeFile file: 'autotestinfo1.txt', text: 'emulator-5554'
                        writeFile file: 'autotestinfo2.txt', text: '6.0'
                        writeFile file: 'autotestinfo3.txt', text: 'http://0.0.0.0:4999/wd/hub'
                        sh 'sudo ${adbHome}/adb connect 165.96.211.138:49110'
                        sh 'sudo ${adbHome}/adb disconnect 165.96.211.138:49110'
                                                //sh 'sudo ${adbHome}/adb connect 172.25.76.146:49110'
                                                //sh 'sudo ${adbHome}/adb disconnect 172.25.76.146:49110'
                        sh 'sudo rm -f testng.xml'
                        sh 'sudo cp -af testng18chimay.xml testng.xml'

                        sh 'sudo ${mvnHome}/mvn test -f pom.xml -DxmlFileName=testng.xml'
                        sh '''sudo javac ReadTxtFile.java
                        sudo java ReadTxtFile'''
                        //publishHTML([allowMissing: false, alwaysLinkToLastBuild: true, keepAll: true, reportDir: 'target/surefire-reports', reportFiles: 'report.html', reportName: 'HTML Report', reportTitles: ''])
                        //archiveArtifacts artifacts: '**/target/surefire-reports/report.html' , fingerprint: true
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