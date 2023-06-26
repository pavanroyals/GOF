pipeline{
    tools{
        jdk 'myjava'
        maven 'mymaven'
    }
    agent none
      stages{
          stage('Checkout'){
              agent any
              steps{
                  git 'https://github.com/dhanvantarisoftware/GOF.git'
              }
          }
          stage('Compile'){
              agent any
              steps{
                  sh 'mvn compile'
              }
          }
          stage('UnitTest'){
              agent{label 'linux_slave'}
              steps{
                  git 'https://github.com/dhanvantarisoftware/GOF.git'
                  sh 'mvn test'
              }
              post{
                  always{
                      junit 'gameoflife-web/target/surefire-reports/*.xml'
                  }
              }
          }
          stage('Package'){
              agent any
              steps{
                  sh 'mvn package'
              }
          }
         
      }
    
}
