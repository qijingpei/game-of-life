import groovy.json.JsonSlurperClassic
jenkinsServer = "http://webclient-jenkins.eng.vmware.com:8080/"

jobConfig = [:]
configURL = 'http://webclient-jenkins.eng.vmware.com:8181/config.json'
configKey = env.JOB_NAME.replaceAll('-', '_')	//replace
dataRepo = 'data_repo'
videoDir = ''

try {
   def response = httpRequest url: configURL, ignoreSslErrors: true
   def config = new JsonSlurperClassic().parseText(response.content)
   jobConfig = config[configKey]
   echo jobConfig.toString()
   dataRepo = config[dataRepo]
   echo "dataRepo $dataRepo"
} catch (err) {
   println("Catching the exception:");
   println(e);
}

nodes = jobConfig.nodes	

def clean_temp(){//clean the temp file
	for (n in nodes)  {
		def nodeName = n.slaveName
        	//def nodeName = "slave1"
		node(nodeName){
   			timeout(time:8, unit: 'SECONDS') {
        		bat "rd /s /q %temp%"
        		//bat "shutdown -r -t 5"
    			}
		}
	}
	parallel deployJobs
}

stage('Build'){
    try {
        timeout(time:10, unit: 'SECONDS') {
            clean_temp()
        }
    }
    catch(Exception e) {
        println("Catching the exception:");
        println(e);
    }
}
