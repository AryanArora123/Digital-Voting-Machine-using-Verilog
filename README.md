# Digital-Voting-Machine-using-Verilog
This project Implemented Verilog based Digital Voting Machine which allows voters to cast votes via button presses or count & display vote results using LEDs
Simulation Results on Aldec Riviera-PRO simulator of a sample testbench are attached here.

# ButtonControl Module
The 'buttonControl' module ensures that a valid vote is only registered if the button is pressed continuously for 10 clock cycles. This helps in debouncing the button press and ensures that accidental or short presses do not count as valid votes.
The module uses a counter to track the duration of the button press and outputs a valid_vote signal when the required duration is met.
# ModeControl Module
The modeControl module is designed to manage the LED display based on the mode of the voting system and whether a valid vote has been cast. It handles two primary modes: voting mode and result mode
This block ensures that the correct visual feedback is provided based on the current voting mode and button activity.
Drives the 8-bit LED display to show either all LEDs lit (if any valid vote has been cast) or the vote count for a selected candidate when their button is pressed.
# VoteLogger Module
When valid_vote is set to 1, it affects this module by incrementing the vote count for the corresponding candidate if the mode is 0 (voting mode)
# Voting Machine
Integrates the above modules to simulate a complete voting machine system. It manages button inputs, processes votes, logs them, and controls LED displays to show results.
Integrates buttonControl and voteLogger modules to handle vote casting for four candidates and tracks each candidate's vote count, controlled by buttons
