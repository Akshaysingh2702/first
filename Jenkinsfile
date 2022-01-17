def parameters() {
workspace = env.WORKSPACE
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
                workspace=get_workspace()
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
def get_workspace()
{ return workspace
}
node {
    stage('parameters') {
          workspace = env.WORKSPACE

        parameters()
     
   
        
    }
}
