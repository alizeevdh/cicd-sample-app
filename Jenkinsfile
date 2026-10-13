   node {
    // De Preparation dient ervoor om van nul te starten met creëren voordat de rest van de pipeline van start gaat
       stage('Preparation') {
           catchError(buildResult: 'SUCCESS') {
               sh 'docker stop samplerunning'
               sh 'docker rm samplerunning'
           }
       }
       stage('Build') {
           build 'BuildSampleApp'
           // Dit zorgt ervoor dat de applicatie opnieuw wordt gebouwd
       }
       stage('Results') {
           build 'TestSampleApp'
       }
   }