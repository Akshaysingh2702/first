def workspace
node {
    workspace = env.WORKSPACE
}

 properties([parameters([
    [$class: 'ChoiceParameter', 
    choiceType: 'PT_SINGLE_SELECT', 
    description: 'Repository Type: snapshots or releases', 
    filterLength: 1, 
    filterable: false, 
    name: 'repo', 
    script: [
        $class: 'GroovyScript', 
        fallbackScript: [
            classpath: [], 
            sandbox: false, 
            script: 
                "return['Could not retrieve repo']"
        ], 
        script: [
            classpath: [], 
            sandbox: false, 
            script:
                ''' 
                import groovy.json.JsonSlurper
                def jsonSlurper = new JsonSlurper()
                def p= "echo ${env:WORKSPACE}".execute().text
                p=p.trim()
                def path = p+'/repo-types.json'
                data = jsonSlurper.parse(new File(path))
                return data
                '''
            ]
        ]
    ]
        ])
])
pipeline {
    agent any;


    
    stages {
        stage('access env variable') {
            steps {
                // in groovy
                echo "${env.WORKSPACE}"
                
                //in shell
                sh 'echo $WORKSPACE'
                
                // in groovy script 
                script {
                    print env.WORKSPACE
                }
            }
        }
    }
}
