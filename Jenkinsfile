import groovy.json.*

jenkinsServer = "http://webclient-jenkins.eng.vmware.com:8080/"
configURL = 'http://webclient-config.eng.vmware.com:8181/api/staticconfig'
jobConfig = [:]
configKey = env.JOB_NAME.replaceAll('-', '_')

def response = httpRequest url: configURL, ignoreSslErrors: true
def config = new JsonSlurperClassic().parseText(response.content)
jobConfig = config[configKey]
echo jobConfig.toString()
/*
defaultEmailList = ['bnie@vmware.com', 'songlil@vmware.com', 'tzhao@vmware' +
      '.com', 'yuez@vmware.com']
*/
/*
defaultEmailList = ['jingpeiq@vmware.com']

jobConfig = [:]
configURL = 'http://webclient-config.eng.vmware.com:8181/api/staticconfig'
configKey = env.JOB_NAME.replaceAll('-', '_')
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
   node('master') {
      echo "failed in initial setup"
     
      //emailext attachLog: true,
      //      body: "${env.BUILD_URL}", subject: "Failed to get configuration", to:
      //      defaultEmailList.join('; ')
      
      sh "exit 1"
   }
}
*/
