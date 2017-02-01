node() {
    stage('checkout') {
        checkout scm
    }

    stage('build') {
        docker.image('barracksiot/nrf5_sdk_docker:12.2.0').inside() {
            sh 'make -C blinky/pca10028/blank/armgcc clean default && mv blinky/pca10028/blank/armgcc/_build/nrf51422_xxac.hex blinky_pca10028.hex'
            sh 'make -C blinky/pca10028/s130/armgcc clean default && mv blinky/pca10028/s130/armgcc/_build/nrf51422_xxac.hex blinky_pca10028_s130.hex'
            sh 'make -C blinky/pca10031/blank/armgcc clean default && mv blinky/pca10031/blank/armgcc/_build/nrf51422_xxac.hex blinky_pca10031.hex'
            sh 'make -C blinky/pca10031/s130/armgcc clean default && mv blinky/pca10031/s130/armgcc/_build/nrf51422_xxac.hex blinky_pca10031_s130.hex'
            sh 'make -C blinky/pca10040/blank/armgcc clean default && mv blinky/pca10040/blank/armgcc/_build/nrf52832_xxaa.hex blinky_pca10040.hex'
            sh 'make -C blinky/pca10040/s132/armgcc clean default && mv blinky/pca10040/s132/armgcc/_build/nrf52832_xxaa.hex blinky_pca10040_s132.hex'
            sh 'make -C blinky/pca10056/blank/armgcc clean default && mv blinky/pca10056/blank/armgcc/_build/nrf52840_xxaa.hex blinky_pca10056.hex'
        }
    }

    stage('archive') {
        archiveArtifacts "*.hex"
    }
}
