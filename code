const int motorPin =9;
const int buttonPin =2;
const int potPin =A0;

enum State {
  OFF,
  MANUAL,
  AUTO
};

State currentState = OFF;

bool lastButton = HIGH;


void setup() {
  // put your setup code here, to run once:
  pinMode(motorPin,OUTPUT);
  pinMode(buttonPin,INPUT_PULLUP);

  Serial.begin(9600);

  Serial.println("STARTED");

}

void loop() {
  // put your main code here, to run repeatedly:
  bool currentButton = digitalRead(buttonPin);

if(lastButton == HIGH && currentButton == LOW) {

    switch(currentState) {

      case OFF:
        currentState = MANUAL;
        Serial.println("MANUAL");
        Serial.print("State =");
Serial.println(currentState);
        break;

      case MANUAL:
        currentState = AUTO;
        Serial.println("AUTO");
        Serial.print("State =");
Serial.println(currentState);
        
        break;

      case AUTO:
        currentState = OFF;
        Serial.println("OFF");
        Serial.print("State =");
Serial.println(currentState);
        break;
    }

    delay(200);
}

lastButton = currentButton;

int potValue = analogRead(potPin);

int pwmValue = map(potValue,0,1023,0,255);

switch(currentState) {

  case OFF:

    analogWrite(motorPin, 0);

    break;

  case MANUAL:

    analogWrite(motorPin, pwmValue);

    Serial.print("PWM:");
Serial.println(pwmValue);
    

    break;

  case AUTO:

  if(potValue < 300) {

    analogWrite(motorPin, 80);
  }

  else if(potValue < 700) {

    analogWrite(motorPin, 180);
  }

  else {

    analogWrite(motorPin, 255);
  }

  Serial.print("Pot = ");
Serial.println(potValue);


  break;
}

}
