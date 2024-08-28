#!/user/bin/env groovy
def bob = "./bob/bob"
def ci_ruleset = "ci/common_ruleset2.0.yaml"

if(env.RELEASE) {
    stage('Custom Publish') {
       withCredentials([usernamePassword(credentialsId: 'SELI_ARTIFACTORY', usernameVariable: 'SELI_ARTIFACTORY_REPO_USER', passwordVariable: 'SELI_ARTIFACTORY_REPO_PASS')]) {
            sh "${bob} -r ${ci_ruleset} upload-mvn-jars"
            sh "${bob} -r ${ci_ruleset} publish-jars"
        }
    }
}