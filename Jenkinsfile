node('master') {
    stage 'Checkout'
    print "DEBUG: parameter isFoo = ${params.isFoo}"
    checkout scm

    stage 'Build'
    sh "./gradlew clean assembleDebug"

    stage 'Archive'
    archiveArtifacts artifacts: 'app/build/outputs/apk/*.apk', excludes: 'app/build/outputs/apk/*-unaligned.apk'
}
