node {
    checkout scm
    docker.withRegistry('https://hub.docker.com/', 'Dockerhub') {

        def customImage = docker.build("my-image:${env.BUILD_ID}")
        
        chmod 666 /var/run/docker.sock

        /* Push the container to the custom Registry */
        customImage.push()
    }
}
