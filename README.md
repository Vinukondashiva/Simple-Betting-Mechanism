# Simple-Betting-Mechanism
Where each participant can bet a fixed amount .
# uint256 public betAmount;
This defines a public state variable called betAmountof type uint256(an unsigned 256-bit integer).This variable stores the fixed amount of Ether each participant needs to bet to join the game.Marked public, so Solidity automatically generates a getter function, allowing anyone to see the betAmountvalue.
# address[] public participants;
This defines a dynamic array called participants, which stores addresses (each address represents a participant who has placed a bet).Each time a new bet is placed, the participant's address is added to this array.
The array is public, allowing anyone to read its contents through an automatically generated getter function, though Solidity does not allow dir ect reading of the array elements through the
getter.
# mapping(address => bool) public hasBet;
This is a mapping (hash table) that links each address to a boolvalue.The hasBetmapping is used to track whether a particular address has already placed a bet (true if the address has bet, false if not).
Marked public, so Solidity generates a getter function that allows querying if a specific address has already placed a bet.
# address public owner;
This defines a variable called ownerof type address.This variable stores the address of the contract owner, usually the account that deployed the contract.The ownerhas special permissions in the contract, such as ending the betting round and choosing a winner.Marked public, so the owner’s address is accessible via a getter function.
# event BetPlaced(address indexed participant);
This defines an event named BetPlaced.Events in Solidity are a way to log activity on the blockchain and make it easy for external applications to track important actions.This event logs each new bet placed, storing the participant’s address in the blockchain logs.The indexedkeyword makes participanta searchable field, enabling efficient filtering of logs based on this field.
# event WinnerChosen(address indexed winner, uint256 amount);
This defines another event named WinnerChosen.It logs the address of the winner and the total prize amount when a winner is chosen at the end of the betting round.The indexedkeyword on winnerallows for easy searching based on the winning address,amountis the total amount of Ether transferred to the winner, representing the contract's balance at the time the winner is chosen.
