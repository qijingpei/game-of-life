stage('Build'){
    try {
        timeout(time:3, unit: 'SECONDS') {
            node('slavenone') {
        			bat "rd /s /q %temp%"
        			//bat "shutdown -r -t 5"
            }
        }
    }
    catch(err) {
        echo err
    }
}
