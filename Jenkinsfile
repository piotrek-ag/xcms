node('XCMS-JENKINS-AGENT'){
	stage('SCM'){
		checkout([$class: 'GitSCM', branches: [[name: '*/jenkins_setup']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/piotrek-ag/xcms']]])
	}
	stage('Build'){
		try{
		sh './mvnw compile'
		}finally{
		archiveArtifacts artifacts: 'target/*.*'
		}
	}
	stage('Test'){
		echo 'Execute unit tests'
	}
	stage('Package'){
		echo 'Zip it up'
	}
	stage('Deploy'){
		echo 'Push to deployment'
	}
	stage('Archive'){
		archiveArtifacts artifacts: 'target/*.*'
	}
}