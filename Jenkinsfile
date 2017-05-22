import groovy.json.JsonSlurperClassic
stage('Build'){
    try {
        timeout(time:30, unit: 'SECONDS') {
            node('slavenone') {
        			bat "rd /s /q %temp%"
        			//bat "shutdown -r -t 5"
            }
        }
    }
    catch(err) {
        
    }
}
