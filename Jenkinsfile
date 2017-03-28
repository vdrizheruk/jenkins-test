node() {
    docker.withRegistry('hub.docker.com', 'hub.docker.com') {
    
        git url: "https://github.com/vdrizheruk/jenkins-test.git", credentialsId: 'github.com'
    
        sh "git rev-parse HEAD > .git/commit-id"
        def commit_id = readFile('.git/commit-id').trim()
        println commit_id
    
    
        stage "publish"
        app.push 'master'
        app.push "${commit_id}"
    }
}
