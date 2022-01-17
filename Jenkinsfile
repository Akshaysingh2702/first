def parameters() {
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
                def path = workspace+'/repo-types.json'
                data = jsonSlurper.parse(new File(path))
                return data
                '''
            ]
        ]
    ]
       ])
])
}



node {
  environment {
        // optional, not used below. Use only if you need to have an environment variable
        workspace = WORKSPACE
    }

    stage('parameters') {

        parameters()
     
   
        
    }
}
