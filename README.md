# 12 HR DIGITAL CLOCK WITH WEEKDAY COUNTER


## Team Details
<details>
   <summary>Detail</summary>
   
>Semester:3rd Sem B. Tech, CSE

>Section :S1

>Member-1:ADITHYA B M , 221CS104 ,adithyabm.221cs104@nitk.edu.in

>Member-2:ARUN M MYAGERI , 221CS113 ,arunmmyageri.221cs113@nitk.edu.in

>Member-3:KETHAVATH MUNI , 221CS131 ,kethavathmuni.221cs131@nitk.edu.in
 </details>


## Abstract
<details>
  <summary>Detail</summary>
A 12-hour digital clock with a weekday counter is a digital timekeeping device that displays time in a 12-hour format, with AM (Ante Meridiem) and PM (Post Meridiem) indications. It also provides the functionality to keep track of the weekday Digital clocks are ubiquitous in our daily lives, and understanding how they work can be a fascinating journey into the world of digital electronics. The "12-Hour Digital Clock with AM/PM Toggle" project is an exploration of digital logic circuits, sequential logic, and the fundamentals of timekeeping. This project is often a stepping stone for students and electronics enthusiasts to learn and apply their knowledge in a hands-on manner.   


Motivation:
----------
> Motivation for this project stems from various factors that include may be of educational purpose , professional development, hands on learning , clock customization, fun and challenge ,learning about the counters and etc.

Unique Contribution :
--------------------
>"Our digital 12-hour clock boasts a sleek, minimalist design that seamlessly blends with modern decor, making it a unique and stylish addition to any room."

>"With a user-friendly interface and intuitive button controls, our clock simplifies time and weekday settings, providing a hassle-free experience."

>In market we have seen lot of clocks but our clock consist of week count also. 

Function :
---------
>• Digital Logic Circuits: The project delves into the basics of digital logic circuits, offering a practical demonstration of how flip-flops, counters, and 
   logic gates can be used to create a functional timekeeping system.
>• Sequential Logic: It introduces the concept of sequential logic, emphasizing the importance of state machines in keeping track of time.
>• Flip-Flop Operation: The utilization of JK flip-flops to store and update time, information provides an opportunity for individuals to understand flip-flop operation and its role in data storage.
>• Binary Counting: The project showcases binary counting as a means of representing hours and minutes, reinforcing binary concepts and their practical applications.
>• Display Technology: The use of 7-segment displays illustrates how digital information is visually presented, giving insight into LED technologies and multiplexing displays.
>• Timekeeping Fundamentals: Through this project, learners gain insights into the fundamental concepts of timekeeping, including the 12-hour clock format and the differentiation between AM and PM.

</details>




## Working
<details>
   <summary>Detail</summary>
 
   WORKING PRINCIPLE:
   
   Initialization: The system. initializes variables for hours, minutes, seconds, and the day of the week.

   Time Retrieval: The current time is obtained, either from system time or user input.
   
   Display Time: The obtained time is displayed on the digital clock.
   
   AM/PM Check: The system checks whether the current time is in the AM or PM.
   
   Weekday Update: The day of the week is updated based on the current time. 
   
   Weekday Display: The updated day of the week is displayed alongside the time.
   
   Midnight Check: If the time is midnight (12:00 AM), the weekday counter resets to the first day of the week.
   
   Time Increment: Seconds are incremented, and checks are performed for reaching 60 seconds, 60 minutes, and 12 hours.
   
   Display Update: The digital clock display is updated with the new time and weekday information.

  INPUTS:
  
   • Clk (Clock Signal): Represents the clock signal.

   • AM_PM_Toggle: Toggle signal to switch between AM and PM.

   • Hour (0-11): Represents the current hour(in a 12-hour format).

  • Minute (0-59): Represents the current minute.

  • Seconds (0-59):Represents the current seconds.

  • 3 : 8 decoder for week day representation.

OUTPUTS:

  • Hour_Display (0-11): The displayed hour on the 7-segment display.

  • Minute_Display (00-59): The displayed minute on the 7-segment display.

  • Second_Display ( 00-59): The displayed second on the 7-segment display.

  • AM_LED: LED indicator for AM.

  • PM_LED: LED indicator for PM.

  • Weekday Counter with decoder.

FUNCTION TABLE:
![image](https://github.com/ADITHYASHETTY123/Digital_clock/assets/150215004/7fcb2ec2-af73-4feb-acc5-983ba4de9d01)

Flow chart:
![image](https://github.com/ADITHYASHETTY123/Digital_clock/assets/150215004/1ac0d006-22fb-46d0-a746-281bc81ca8aa)

</details>

## Logisim Circuit Diagram
<details>
   <summary>Detail</summary>
   
   ![image](https://github.com/ADITHYASHETTY123/Digital_clock/assets/150215004/19b7e2d8-8c08-48ba-9e6e-b256cd5e13aa)

</details>

## Verilog Code 
<details>
   <summary>Detail</summary>
   "Digital_Clock.v"

   
    module Digital_Clock(
    Clk_1sec,  
    reset,    
    seconds,
    minutes,
    hours);


    input Clk_1sec;  
    input reset;

    output [5:0] seconds;
    output [5:0] minutes;
    output [4:0] hours;

    reg [5:0] seconds;
    reg [5:0] minutes;
    reg [4:0] hours; 

    always @(posedge(Clk_1sec) or posedge(reset))
    begin
    if(reset == 1'b1) begin
        
        seconds = 0;
        minutes = 0;
        hours = 0;
    end
    else if(Clk_1sec == 1'b1) begin  
        seconds = seconds + 1;
        if(seconds == 60) begin 
            seconds = 0;  
            minutes = minutes + 1;
            if(minutes == 60) begin 
                minutes = 0; 
                hours = hours + 1;  
                if(hours ==  24) begin  
                    hours = 0; 
                end 
            end
        end     
    end
    end

    endmodule


   

TESTBENCH FILE:
"tb_clock.v"


    module tb_clock;

    // Inputs
    reg Clk_1sec;
    reg reset;
    // Outputs
    wire [5:0] seconds;
    wire [5:0] minutes;
    wire [4:0] hours;

    // Instantiate the Unit Under Test (UUT)
    Digital_Clock uut (
        .Clk_1sec(Clk_1sec), 
        .reset(reset), 
        .seconds(seconds), 
        .minutes(minutes), 
        .hours(hours)
    ); 
    
    //Generating the Clock with `1 Hz frequency
    initial Clk_1sec = 0;
    always #50000000 Clk_1sec = ~Clk_1sec;  //Every 0.5 sec toggle the clock.

    initial begin
        reset = 1;
        // Wait 100 ns for global reset to finish
        #100;
        reset = 0;  
    end      
    endmodule
</details>

