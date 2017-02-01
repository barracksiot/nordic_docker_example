/*
 * Copyright 2017 Barracks Solution Inc.
 *
 * Licensed under the Apache License, Version 2.0 (the "License");
 * you may not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 *
 *     http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS,
 * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 */
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
