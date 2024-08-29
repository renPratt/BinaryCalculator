# BinaryCalculator
An assignment for a Computer Organization class which was intended to make sure we had a comprehensive understanding of binary, and how it works as a base language within computers. It multiplies, divides, adds, and subtracts using only boolean logic.

### Overview
The **BinaryCalculator** class is a utility for performing basic arithmetic operations—addition, subtraction, multiplication, and division—on binary numbers represented by the BitField class. The class uses bitwise operations to carry out these calculations, which is efficient for binary arithmetic.

### Methods
#### 1. add(BitField a, BitField b) -> BitField
This method adds two binary numbers represented as BitField objects. The method handles bitwise addition, including managing carry-overs (referred to as "remains" in the code).

###### Example:
###### If both bits are 1, the sum is 0 with a carry-over.
###### If one bit is 1 and the other is 0, the sum is 1.
###### The carry-over is managed in subsequent operations.

#### 2. subtract(BitField a, BitField b) -> BitField
The subtraction method calculates the result of subtracting b from a by using two's complement. The method first computes the complement of b and then adds it to a.

###### Special Cases:
###### 0 - b = -b: If a is zero, the method returns the two's complement of b.
###### Special handling for certain edge cases involving small bitfields.

#### 3. multiply(BitField a, BitField b) -> BitField
This method performs multiplication of two binary numbers. It uses a bitwise shifting approach where if a bit in a is 1, it adds a shifted version of b to the result.

###### Example:
###### If a[i] = 1, the method adds b shifted left by i positions to the result.

#### 4. divide(BitField a, BitField b) -> BitField[]
The divide method returns both the quotient and remainder of dividing a by b. It handles division by ensuring that dividing by zero returns null and handles cases where a is smaller than b.

###### Special Cases:
###### a == b: The quotient is 1, and the remainder is 0.
###### a < b: The quotient is 0, and the remainder is a.

#### 5. complement(BitField a) -> BitField
This helper method computes the bitwise complement of a BitField by flipping each bit.

### Design Considerations
#### Efficiency: The methods are designed to be efficient in bitwise operations, crucial for binary arithmetic.
#### Edge Cases: Special attention is given to handling edge cases, such as subtraction and division by zero, as well as small bitfields.

### Conclusion
The BinaryCalculator class provides a robust foundation for binary arithmetic, ensuring correctness and handling edge cases with care. This implementation is suitable for applications requiring efficient binary calculations.
