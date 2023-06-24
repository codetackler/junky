pipeline {
  agent any
  triggers {
    fanin(upstreamProjects: "janky/master")
  }
  parameters {
    extendedChoice(
      name: 'HOST_PLATFORMS',
      type: 'PT_MULTI_SELECT',
      value: 'debian_amd64,debian_arm64,debian_i386,debian_armv7hf',
      defaultValue: 'debian_amd64'
    )
    choice(name: 'BUILD_MODE', choices: ['release','debug'])
  }
  stages {
    stage('Junky') {
      steps {
        echo "${HOST_PLATFORMS}"
        echo "${BUILD_MODE}"
        sh '''
            echo "Hola"
            sleep 10
        '''
      }
    }
  }
}
