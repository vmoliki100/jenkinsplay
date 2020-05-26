pipeline {

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/vmoliki100/jenkinsplay.git', branch:'test-deploy-stage'
      }
    }

   
   stage('Deploy Application on K8s') {
		steps {
			withKubeConfig([credentialsId: 'Kubernetes_Configuration_File',
			serverUrl: 'https://ED1BE355533A7CF9674C747B71B48E40.sk1.us-east-2.eks.amazonaws.com',
			clusterName: 'aps-cmseks-east2']){
				sh("kubectl apply -f nginx.yaml")
			}     
		}
     }
  
}

}
