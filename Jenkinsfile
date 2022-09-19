#!/usr/bin/env groovy

@Library("build-jenkins-shared-library@feat/rundeck_integration") _

import static com.dericon.jenkins.Constants.MASTER_BRANCH_NAME

genericNodeBuild('14.19.3') {
    sh 'PLAYWRIGHT_SKIP_BROWSER_DOWNLOAD=1 npm ci'
    sh 'npm run detect-version'
    sh 'npm run lint'
    sh 'npm run test'
    sh 'node --max_old_space_size=3000 ./node_modules/.bin/ng build'
}
