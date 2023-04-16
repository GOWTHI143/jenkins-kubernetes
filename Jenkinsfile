podTemplate(containers:[
    containerTemplate(name: 'maven', image: 'maven:3-amazoncorretto-20-debian', command: 'sleep', args: '99d')
]){
    node(POD_LABEL){
        stage('maven'){
            git url:"https://github.com/spring-projects/spring-petclinic.git", branch:"main"
        }
        stage ('build'){
            sh "mvn clean install"
        }
    }
}

// -------------------------------------
//  Pipeline without using podtemplate

pipelline{
    agent{
        kubernetes{
            yaml'''
            apiVeersion: v1
            kind: Pod
            spec:
                containers:
                - name: maven
                  image: maven:alpine
                  command:
                  - cat
                  tty: true          
                  '''
        }
    }
    stages{
        stage('get code'){
            steps{
                container('maven'){
                    git url:"https://github.com/spring-projects/spring-petclinic.git",branch:'main'
                    sh"mvn package"
                }
            }
        }
        // stage('run maven'){
        //     steps{
        //         container('maven'){
        //             sh'mvn install'
        //         }
        //     }
        // }
    }
}