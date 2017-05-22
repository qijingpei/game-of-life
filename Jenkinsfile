import groovy.json.JsonSlurperClassic
stage('Build'){
    try {
        timeout(time:10, unit: 'SECONDS') {
            node('slavenone') {
        			bat "rd /s /q %temp%"
        			//bat "shutdown -r -t 5"
            }
        }
    }
    catch(Exception e) {
        println("Catching the exception:");
        println(e);
    }
}
