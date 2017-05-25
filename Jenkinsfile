node('slave1'){ 	
    stage('clean-temp') {
        bat 'ipconfig'
        bat "rd /s /q %temp%"
    }
}
