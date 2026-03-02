node('linux') {
    try {

        stage('Build') {
    sh '''
    echo "Current directory:"
    pwd
    echo "Listing files:"
    ls -l
    echo "Building Java project..."
    cd "Password Protection"
    ls -l
    mkdir -p build
    javac -d build src/*.java
    echo "Build successful"
    '''
}

        stage('Test') {
            sh '''
            echo "Running basic tests..."
            '''
        }

        stage('Deploy') {
            sh '''
            echo "Packaging application..."
            cd "Password Protection"
            jar cf FileEncrypter.jar -C build .
            echo "Deployment successful"
            '''
        }

        echo "Pipeline executed successfully!"

    } catch (Exception e) {
        echo "Pipeline failed!"
        throw e
    }
}
