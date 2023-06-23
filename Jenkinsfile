pipeline {
  agent any
  triggers {
    upstream(upstreamProjects: "janky/master",
             threshold: hudson.model.Result.SUCCESS)
  }
  parameters {
    extendedChoice(
      name: 'HOST_PLATFORMS',
      type: 'PT_MULTI_SELECT',
      value: 'debiam_amd64,debian_arm64,debian_i386,debian_armv7hf',
      defaultValue: 'release'
    )
    choice(name: 'BUILD_MODE', choices: ['release','debug'])
  }
  stages {
    stage('Junky') {
      steps {
        sh '''
            echo "Hola"
            sleep 10
        '''
      }
    }
  }
}
