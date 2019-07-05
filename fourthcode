int ledPin=12; 
char* letters[]={
   ".-","-...","-.-.","-..",".","..-.","--.","....","..",   //a-i
   ".---","-.-",".-..","--","-.","---",".--.","--.-",".-.",  //j-r
   "...","-","..-","...-",".--","-..-","-.--","--.."      //s-z   
}; 
char* numbers[]={
   "-----",".----","..---","...--","....-",".....","-....","--...",
   "---..","----." //0-9 
}; 
int dotDelay=200;
void setup(){
    pinMode(12,OUTPUT);
    Serial.begin(9600); 
} 
void loop(){
    char ch;
    if (Serial.available()){
        ch=Serial.read();
        if (ch>'a'&& ch<='z'){
            flashSequence(letters[ch-'a']);      
        }       
        else if (ch>='0' && ch<='9'){
            flashSequence(numbers[ch-'0']);
        }       
        else if (ch==' '){
            delay(dotDelay*4);
        }
   } 
} 
void flashSequence(char* sequence) {
    int i=0;
    while (sequence[i]!=NULL){
        flashDotOrDash(sequence[i]);
        i++;
    } 
    delay(dotDelay*3);
    } 
void flashDotOrDash(char dotOrDash){
    digitalWrite(12,HIGH);
    if(dotOrDash=='.'){
        delay(dotDelay);
    }    
    else { 
        delay(dotDelay*3);
    }    
    digitalWrite(12,LOW);    
    delay(dotDelay);
}
