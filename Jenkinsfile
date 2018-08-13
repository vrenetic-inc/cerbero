@Library('vrenetic-jenkins-shared')

def agentLabel = "Mac_build_slave"

properties([
  parameters([
    booleanParam(
      name: 'release',
      defaultValue: false,
      description: 'Release to Nexus')
  ])
])

node(agentLabel) {
  ws ("/Users/administrator/workspace/${env.JOB_NAME}-${env.BRANCH_NAME}") {
  stage('setup') {
    def gitStats = checkout scm
    env._GIT_COMMIT = gitStats["GIT_COMMIT"].substring(0, 4)

    gstCerbero.setup()
  }

  stage('test') {
    ansiColor('xterm') {
      echo "No tests for gstreamer yet!"
    }
  }

  stage('release') {
    gstCerbero.build()
  }
}
}

