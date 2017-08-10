node {
    /* Configure the JDK to use. 'JDK8' is the symbolic name under which the JDK
     * is defined in the global Jenkins configuration. */
    env.JAVA_HOME="${tool 'java8'}"

    stage 'Build'
    /* Clone the project from github */
    git url: 'https://github.com/jcsirot/atmosphere-calculator.git', branch: '0.1.0'
    /* Select the maven configuration. 'm3' is the symbolic name used the
     * global Jenkins configuration. */
    def mvnHome = tool "m3"
    /* Run maven: build and run the unit tests  */
    sh "${mvnHome}/bin/mvn clean package"
    /* This is the syntax for using a generic step. Here the test results are archived. */
    step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
}
