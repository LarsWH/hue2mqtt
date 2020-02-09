docker run -d -p 1883:1883 -p 9001:9001 --name mqtt eclipse-mosquitto
docker exec -it mqtt /bin/bash


docker run -it -p 1883:1883 -p 9001:9001 --name mqtt eclipse-mosquitto
docker run -it -p 1883:1883 -p 9001:9001 -v mosquitto.conf:/mosquitto/config/mosquitto.conf eclipse-mosquitto


Build jar:
	gradlew clean build
The jar is located here:
	build\libs\hue2mqtt.jar 
Run the jar:	
	java -jar build\libs\hue2mqtt.jar
	java -jar build\libs\hue2mqtt.jar -Dhue2mqtt.bridge.id=Philips-hue
	java -jar build\libs\hue2mqtt.jar -Dhue2mqtt.bridge.ip=192.168.0.39
	
	
IntelliJ:
	Add run configuration:
		Seledct '+' 
		Select "JAR application"
		Browse to the JAR file
		Add environment variables...
		Add system properties....
		"Before lauch: "  tryk på "+" og tilføj et Gradle task (browse til 'build.gradle' og tilføj task 'build')
	Now it is possible to use break points...	
