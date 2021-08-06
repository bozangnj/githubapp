@Library("CitrixSharedLibrary") _
import java.text.SimpleDateFormat
import java.util.Date
import groovy.json.JsonOutput
import groovy.json.JsonSlurperClassic


node("docker && linux") {
  deleteDir()
  dir("${env.WORKSPACE}/pacman_config") {
    pacmanWithGitCredentials.httpGitCredentials("github-app-boz") {
          sh "git clone https://github.com/bozangnj/test-action.git"
          sh "cd test-action"
          sh "ls"
          sh "git branch"
          sh "git pull origin master"
          writeFile file: "lastDeployDateOfPacmanEa", text: "hello"
          sh "git add lastDeployDateOfPacmanEa; git commit -m 'update the ea deploy time'; git push origin master"
        }
  }
}