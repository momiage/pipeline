pipeline {
  agent any
  stages {
    stage('parallel job1 for No.11 with No.16') {
      parallel {
        stage('No11:Windows for print job Slave') {
          agent {
            label 'Slave'
          }
          steps {
            echo 'start'
            dir(path: 'Windows') {
              bat 'WindowsCase_11_New.au3'
              bat '''javac ReadTxtFile.java
                                                                        java ReadTxtFile'''
            }
            
          }
        }
        stage('No16:KB opetaion') {
          agent {
            label 'master'
          }
          steps {
            retry(count: 3) {
              writeFile(file: 'autotestinfo1.txt', text: '165.96.211.138:49110')
              writeFile(file: 'autotestinfo2.txt', text: '4.2.2')
              writeFile(file: 'autotestinfo3.txt', text: 'http://0.0.0.0:4990/wd/hub')
              sh 'sudo ${adbHome}/adb connect 165.96.211.138:49110'
              sh 'sudo rm -f testng.xml'
              sh 'sudo cp -af testng16chimay.xml testng.xml'
              sh 'sudo ${mvnHome}/mvn test -f pom.xml -DxmlFileName=testng.xml'
              sh '''sudo javac ReadTxtFile.java
                                                            sudo java ReadTxtFile'''
            }
            
          }
          post {
            always {
              publishHTML(allowMissing: false, alwaysLinkToLastBuild: false, keepAll: true, reportDir: 'target/surefire-reports', reportFiles: 'report.html', reportName: 'HTML Report', reportTitles: '')
              
            }
            
          }
        }
      }
    }
    stage('No13:natvie cheetah') {
      agent {
        label 'master'
      }
      steps {
        retry(count: 3) {
          writeFile(file: 'autotestinfo1.txt', text: '165.96.211.138:49110')
          writeFile(file: 'autotestinfo2.txt', text: '4.2.2')
          writeFile(file: 'autotestinfo3.txt', text: 'http://0.0.0.0:4990/wd/hub')
          sh 'sudo ${adbHome}/adb connect 165.96.211.138:49110'
          sh 'sudo rm -f testng.xml'
          sh 'sudo cp -af testng13chimay.xml testng.xml'
          sh 'sudo ${mvnHome}/mvn test -f pom.xml -DxmlFileName=testng.xml'
          sh '''sudo javac ReadTxtFile.java
                                                  sudo java ReadTxtFile'''
        }
        
      }
      post {
        always {
          publishHTML(allowMissing: false, alwaysLinkToLastBuild: false, keepAll: true, reportDir: 'target/surefire-reports', reportFiles: 'report.html', reportName: 'HTML Report', reportTitles: '')
          
        }
        
      }
    }
    stage('No14:webpage') {
      agent {
        label 'master'
      }
      steps {
        retry(count: 3) {
          writeFile(file: 'autotestinfo1.txt', text: 'emulator-5554')
          writeFile(file: 'autotestinfo2.txt', text: '6.0')
          writeFile(file: 'autotestinfo3.txt', text: 'http://0.0.0.0:4999/wd/hub')
          sh 'sudo ${adbHome}/adb connect 165.96.211.138:49110'
          sh 'sudo ${adbHome}/adb disconnect 165.96.211.138:49110'
          sh 'sudo rm -f testng.xml'
          sh 'sudo cp -af testng14chimay.xml testng.xml'
          sh 'sudo ${mvnHome}/mvn test -f pom.xml -DxmlFileName=testng.xml'
          sh '''sudo javac ReadTxtFile.java
                                  sudo java ReadTxtFile'''
        }
        
      }
      post {
        always {
          publishHTML(allowMissing: false, alwaysLinkToLastBuild: false, keepAll: true, reportDir: 'target/surefire-reports', reportFiles: 'report.html', reportName: 'HTML Report', reportTitles: '')
          
        }
        
      }
    }
    stage('No17:reset machine webpage') {
      agent {
        label 'master'
      }
      steps {
        retry(count: 3) {
          writeFile(file: 'autotestinfo1.txt', text: 'emulator-5554')
          writeFile(file: 'autotestinfo2.txt', text: '6.0')
          writeFile(file: 'autotestinfo3.txt', text: 'http://0.0.0.0:4999/wd/hub')
          sh 'sudo ${adbHome}/adb connect 165.96.211.138:49110'
          sh 'sudo ${adbHome}/adb disconnect 165.96.211.138:49110'
          sh 'sudo rm -f testng.xml'
          sh 'sudo cp -af testng17chimay.xml testng.xml'
          sh 'sudo ${mvnHome}/mvn test -f pom.xml -DxmlFileName=testng.xml'
          sh '''sudo javac ReadTxtFile.java
                        sudo java ReadTxtFile'''
        }
        
      }
      post {
        always {
          publishHTML(allowMissing: false, alwaysLinkToLastBuild: false, keepAll: true, reportDir: 'target/surefire-reports', reportFiles: 'report.html', reportName: 'HTML Report', reportTitles: '')
          
        }
        
      }
    }
    stage('No18:powser off machine webpage') {
      agent {
        label 'master'
      }
      steps {
        retry(count: 3) {
          writeFile(file: 'autotestinfo1.txt', text: 'emulator-5554')
          writeFile(file: 'autotestinfo2.txt', text: '6.0')
          writeFile(file: 'autotestinfo3.txt', text: 'http://0.0.0.0:4999/wd/hub')
          sh 'sudo ${adbHome}/adb connect 165.96.211.138:49110'
          sh 'sudo ${adbHome}/adb disconnect 165.96.211.138:49110'
          sh 'sudo rm -f testng.xml'
          sh 'sudo cp -af testng18chimay.xml testng.xml'
          sh 'sudo ${mvnHome}/mvn test -f pom.xml -DxmlFileName=testng.xml'
          sh '''sudo javac ReadTxtFile.java
                        sudo java ReadTxtFile'''
        }
        
      }
      post {
        always {
          publishHTML(allowMissing: false, alwaysLinkToLastBuild: false, keepAll: true, reportDir: 'target/surefire-reports', reportFiles: 'report.html', reportName: 'HTML Report', reportTitles: '')
          
        }
        
      }
    }
    stage('No.19 test') {
      steps {
        echo 'test'
      }
    }
  }
  environment {
    test = 'test'
  }
}