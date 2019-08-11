node()
{
    stage "Checkout Code"
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/nvn17git/nvnshoppingcart']]])
    
    stage "Build Code"
        sh "mvn clean package"
        
    stage "Deploy Application"
        //sh 'rm /var/lib/tomcat/webapps/nvnshoppingcart*'
        sh 'cp **/*.war /var/lib/tomcat/apache-tomcat-8.5.24/webapps/'
}
