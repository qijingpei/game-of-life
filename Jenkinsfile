import groovy.json.JsonSlurperClassic

def clean_temp(){//clean the temp file
	//for (n in nodes)  {
		//def nodeName = n.slaveName
        	def nodeName = "slave1"
		node(nodeName){
   			timeout(time:8, unit: 'SECONDS') {
        		bat "rd /s /q %temp%"
        		//bat "shutdown -r -t 5"
    			}
		}
	//}
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
