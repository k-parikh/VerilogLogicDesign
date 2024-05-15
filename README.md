# VerilogLogicDesign
This project is done in Quartus Prime Lite on a Terasic MAX10 DE 10 Lite FPGA Board. This project contains two different logic gate schematics, which output different results. 

![image](https://github.com/k-parikh/VerilogLogicDesign/assets/105128826/d6f3754e-9dfb-40b3-b0ee-e75910daf6ff)

The figure above represents the first logic design that will be coded in Verilog using Gate-level modeling. 

`TestModule(LEDR[0], SW[0], SW[1], SW[2]);`

This line of code is located in the REG/WIRE DECLARATIONS, where LEDR[0] represents the output and SW[0], SW[1], SW[2] represents the inputs. 

```
module TestModule(x, a, b, c);
	input a, b, c;
	output x;
	wire one, two; 
	
	nand (one, c, b);
	nor (two, b, a);
	or(x, one, two);
	
endmodule
```

This function is located in the STRUCTURAL CODING portion of the file, which is where the actual logic is located. The syntax for the logic gates are logic_gate(output, input1, input2). In this case, there were multiple levels the the logic design, so there needed to be wires to make sure that the values were captured and stored accurately. 

![image](https://github.com/k-parikh/VerilogLogicDesign/assets/105128826/7f3b3014-1df2-4080-b914-ffb4e647c6ae)

This table is represents test cases for the logic design and the results are shown in the figure below.

![image](https://github.com/k-parikh/VerilogLogicDesign/assets/105128826/89abb7b3-5a9d-4d74-a99a-9ba10ec72ff6)

![image](https://github.com/k-parikh/VerilogLogicDesign/assets/105128826/1e8ca3c5-cb84-4422-b5af-3080418e97d8)

The second logic design is slown in the figure above. The same proedure was used to find the results of this logic design. 

`TestModule(LEDR[0], LEDR[1], LEDR[2], SW[0], SW[1], SW[2], SW[3]);`

```
module TestModule(x, y, z, a, b, c, d);
	input a, b, c, d;
	output x, y, z;
	wire one;
	xor (one, d, c);
	xor (x, b, a);
	and (z, d, one);
	nand (y, x, one);

endmodule
```

