# Next Generation IoT 

![alt text](https://github.com/mozamani/nextgeniot/blob/master/files/logo.png) <!-- .element height="10%" width="12%" -->

## Outline
In this hands-on session, we will use [MXCHIP IoT DevKit](https://microsoft.github.io/azure-iot-developer-kit/) as our main IoT physical devices. 
![alt text](https://github.com/mozamani/nextgeniot/blob/master/files/MXChip.png) <!-- .element height="10%" width="12%" -->

These kits are equipied with OLED display, headphone, microphone, sensors like temperature, humidity, motion, pressure and Wifi helping us to build flexible IoT projects quickly. In addition to the DevKit, we would need (depending on the use-case):<br>

1) Azure subscription
2) Azure IoT Hub 
3) Azure Stream Analytics 
4) Azure Machine Learning Service / Azure Machine Learning Studio (Classic)
5) Azure Cognitive Services
6) Azure Functions 
7) PowerBI (for live monitoring dashboard) 

A number of example projects using IoT DevKit can be found [here](https://microsoft.github.io/azure-iot-developer-kit/docs/projects/), including: 
1) [Remote montitoring of temprature, pressure, humidity](https://docs.microsoft.com/en-us/azure/iot-accelerators/iot-accelerators-arduino-iot-devkit-az3166-devkit-remote-monitoring-v2)<br>
2) [Creating a door monitor](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-door-monitor)<br>
3) [Making a voice translator using Azure Cognitive Services](https://docs.microsoft.com/en-us/samples/azure-samples/mxchip-iot-devkit-translator/sample/)<br>
4) [Sending alerts or tweets triggered by the motion sensor](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-translator)<br>

## Reference architecture
Most of the IoT solutions essentially follow the below basic architecture:

![alt text](https://github.com/mozamani/nextgeniot/blob/master/files/ref_arch.png) <!-- .element height="10%" width="12%" -->

1) IoT devices connect to IoT Hub and start sending messages (see an introduction [here](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)) 
2) Iot Hub receives and manages messsages from multiple devices ([link](https://docs.microsoft.com/en-us/azure/iot-hub/))
3) Messages from IoT Hub can either being just stored in a storage unit, trigger a fucntion directly (e.g. [here](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-door-monitor)), or being sent to a processing unit like [Azure Stream Analytics](https://docs.microsoft.com/en-us/azure/stream-analytics/)
4) In addition to it's embedded analytical and machine learning capabilities (see [here](https://docs.microsoft.com/en-us/azure/stream-analytics/stream-analytics-machine-learning-anomaly-detection)), one can also create bespoke ML models using [Azure Machine Learning Services](https://docs.microsoft.com/en-us/azure/machine-learning/) and expose those models to be called from the Stream Analytics functions (see an example [here](https://docs.microsoft.com/en-us/azure/stream-analytics/stream-analytics-machine-learning-integration-tutorial)).

## Example
### Predicting probability of rain with IoT DevKit
![alt text](https://github.com/mozamani/nextgeniot/blob/master/files/weather_arch.png) <!-- .element height="10%" width="12%" -->
We first connect our DevKits to our Azure Event Hubs and start streaming data ([link](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)), then create an Azure Streaming Analytics job and define [input stream](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)) and [output(s)](). Using the [historical weather data](), we can build a machine learning classifier that predicts probability of rain based on measured humidity and temprature levels. We then expose this model as a webservice and call the model using a [stream analytcis function](). Now we can query our stream and start predicting weather live. Results can be either written to an output storage unit or a live [PowerBI dashboard]().   

