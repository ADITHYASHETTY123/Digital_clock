# Digital_clock


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
   
• Digital Logic Circuits: The project delves into the basics of digital logic circuits, offering a practical demonstration of how flip-flops, counters, and logic gates can be used to create a functional timekeeping system.
• Sequential Logic: It introduces the concept of sequential logic, emphasizing the importance of state machines in keeping track of time.
• Flip-Flop Operation: The utilization of JK flip-flops to store and update time, information provides an opportunity for individuals to understand flip-flop operation and its role in data storage.
• Binary Counting: The project showcases binary counting as a means of representing hours and minutes, reinforcing binary concepts and their practical applications.
• Display Technology: The use of 7-segment displays illustrates how digital information is visually presented, giving insight into LED technologies and multiplexing displays.
• Timekeeping Fundamentals: Through this project, learners gain insights into the fundamental concepts of timekeeping, including the 12-hour clock format and the differentiation between AM and PM.

MOTIVATION:
Motivation for this project stems from various factors that include may be of educational purpose , professional development, hands on learning , clock customization, fun and challenge ,learning about the counters and etc.

UNIQUE CONTRIBUTION
• "Our digital 12-hour clock boasts a sleek, minimalist design that seamlessly blends with modern decor, making it a unique and stylish addition to any room."
• "With a user-friendly interface and intuitive button controls, our clock simplifies time and weekday settings, providing a hassle-free experience."
</details>


## Working
<details>
   <summary>Detail</summary>
   This project aims to create a functional 12-hour digital clock with an AM/PM indicator using digital components such as JK flip-flops, 7-segment displays, and binary counters.
   
Key Features:

• 12-Hour Time Format: The clock follows the 12-hour time format commonly used in everyday life.
• AM/PM Indicator: (DECODER) A visible AM/PM toggle indicates whether it is morning or afternoon/evening.
• 7-Segment Displays: Time is displayed using 7-segment LED displays, offering a visual representation of hours and minutes.
• Binary Counters: Binary counters are used to keep track of hours and minutes, promoting an understanding of binary counting.
   
Inputs:

• Clk (Clock Signal): Represents the clock signal.
• AM_PM_Toggle: Toggle signal to switch between AM and PM.
• Hour (0-11): Represents the current hour (in a 12-hour format).
• Minute (0-59): Represents the current minute.
• Seconds (0-59):Represents the current seconds.
• 3 : 8 decoder for week day representation.

Outputs:

• Hour_Display (0-11): The displayed hour on the 7-segment display.
• Minute_Display (00-59): The displayed minute on the 7-segment display.
• Second_Display ( 00-59): The displayed second on the 7-segment display.
• AM_LED: LED indicator for AM.
• PM_LED: LED indicator for PM.
• Weekday Counter

Function Table:

Clk | AM/PM_Toggle |  Hour | Minute | Hour_Display|  Minute_Display | AM_ LED | PM_ LED|
_______________________________________________________________________________________
 0  |      0       |   0   |   0    |     0       |       00        |     1   |    0
 
 1  |      0       |   0   |   1    |     0       |       01        |     1   |    0
 
 0  |      0       |   0   |   2    |     0       |       02        |     1   |    0
 
 1  |      0       |   0   |   3    |     0       |       03        |     1   |    0
________________________________________________________________________________________
 0  |      0       |   1   |   0    |     1       |       00        |     1   |    0
 1  |      0       |   1   |   1    |     1       |       01        |     1   |    0
 0  |      0       |   1   |   2    |     1       |       02        |     1   |    0
 1  |      0       |   1   |   3    |     1       |       03        |     1   |    0
________________________________________________________________________________________
 0  |     0        |   11  |  56    |    11       |       56        |     1   |    0
 1  |     0        |   11  |  57    |    11       |       57        |     1   |    0
 0  |     0        |   11  |  58    |    11       |       58        |     1   |    0
 1  |     0        |   11  |  59    |    11       |       59        |     1   |    0
 0  |     1        |   0   |   0    |     0       |       00        |     0   |    1
 1  |     1        |   0   |   1    |     0       |       01        |     0   |    1
 0  |     1        |   0   |   2    |     0       |       02        |     0   |    1
 1  |     1        |   0   |   3    |     0       |       03        |     0   |    1
___________________________________________________________________________________________
 0  |     1        |  11   |  56    |    11       |       56        |     0   |    1
 1  |     1        |  11   |  57    |    11       |       57        |     0   |    1
 0  |     1        |  11   |  58    |    11       |       58        |     0   |    1
 1  |     1        |  11   |  59    |    11       |       59        |     0   |    1
__________________________________________________________________________________________
</details>
