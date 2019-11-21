
![alt text](https://github.com/mozamani/nextgeniot/blob/master/files/logo.png) <!-- .element height="10%" width="12%" -->


In this hands-on session, we will use [MXCHIP IoT DevKit](https://microsoft.github.io/azure-iot-developer-kit/) as our main IoT physical devices. These kits are equipied with OLED display, headphone, microphone, sensors like temperature, humidity, motion, pressure and Wifi helping us to build flexible IoT projects quickly. In addition to the DevKit, we would need (depending on the use-case):<br>

1) an Azure subscription
2) Azure IoT Hub instance
3) Azure Stream Analytics instance
4) Azure Machine Learning service
5) Azure Cognitive Services
6) Azure Functions 

A number of example projects using IoT DevKit can be found [here](https://microsoft.github.io/azure-iot-developer-kit/docs/projects/), including: 
1) [Remote montitoring of temprature, pressure, humidity](https://docs.microsoft.com/en-us/azure/iot-accelerators/iot-accelerators-arduino-iot-devkit-az3166-devkit-remote-monitoring-v2)<br>
2) [Creating a door monitor](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-door-monitor)<br>
3) [Making a voice translator using Azure Cognitive Services](https://docs.microsoft.com/en-us/samples/azure-samples/mxchip-iot-devkit-translator/sample/)<br>
4) [Sending alerts or tweets triggered by the motion sensor](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-translator)<br>

## Reference architecture
Most of the IoT solutions essentially follow the below basic architecture:

![alt text](https://github.com/mozamani/nextgeniot/blob/master/files/arch.png) <!-- .element height="10%" width="12%" -->

1) IoT devices connect to IoT Hub and start sending messages (see an intro [here](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)) 
2) Iot Hub receives and manages messsages from multiple devices ([link](https://docs.microsoft.com/en-us/azure/iot-hub/))
3) Messages from IoT Hub can either being just stored in a storage unit, trigger a fucntion directly (e.g. [here](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-door-monitor)), or being sent to a processing unit like [Azure Stream Analytics](https://docs.microsoft.com/en-us/azure/stream-analytics/)
4) In addition to it's embedded analytical and machine learning capabilities (see [here](https://docs.microsoft.com/en-us/azure/stream-analytics/stream-analytics-machine-learning-anomaly-detection)), one can also create bespoke ML models using [Azure Machine Learning Services](https://docs.microsoft.com/en-us/azure/machine-learning/) and expose those models to be called from the Stream Analytics functions (see an example [here](https://docs.microsoft.com/en-us/azure/stream-analytics/stream-analytics-machine-learning-integration-tutorial)).

## Examples

