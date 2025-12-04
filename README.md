# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**

1.Start the program.

2.Declare the module name and define the input and output ports.

3.Inputs: J, K, Clock, and Reset.

4.Outputs: Q and QB.

5.Create an always block that is triggered on the positive edge of the clock signal.

6.Inside the always block, first check the reset condition.

7.If the reset input is active, maintain or initialize the outputs as required.

8.When reset is inactive, implement the JK flip-flop logic based on the inputs J and K.

9.If both J and K are 0, the output remains unchanged (Hold condition).

10.If J and K are different, the output follows the value of J (Set or Reset condition).

11.If both J and K are 1, the output toggles (changes to its complement).

12.End the always block and complete the module definition.

13.Simulate the design by applying various combinations of J and K along with clock pulses to observe the hold, set, reset, and toggle conditions.


**PROGRAM**

### Developed by: SUTHAN.B

### RegisterNumber: 25018310

```
module JK_Flip_Flop(q, qb,j,k,clock,reset);
input j,k,clock,reset;
output reg q, qb;
	 
always @ (posedge (clock))

    begin 
        if (!reset)
            begin
               q <= q;
               qb <=qb;
            end
else 
      begin
        if (j==0 && k==0)
		       begin
			    q <= q;
			    q <= qb;
			    end	 
        
        else if (j!=k)
             begin
	          q <= j;
	          qb <= k;
	          end
        else if (j==1 && k==1)
             begin
	          q <= ~q;
	          qb <= ~qb;
	          end
	  
      end
 
end           
endmodule 
```


**RTL LOGIC FOR FLIPFLOPS**
<img width="971" height="428" alt="image" src="https://github.com/user-attachments/assets/1ce2568d-2608-481d-ab1c-bd7c49db1723" />


**TIMING DIGRAMS FOR FLIP FLOPS**
<img width="1916" height="1119" alt="image" src="https://github.com/user-attachments/assets/8d62cc59-d434-4472-8d6c-0ccda3e86628" />


**RESULTS**

Studied and verified the truth table of JK flip-flop in  Quartus II using verilog programming successfully.
