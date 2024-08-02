from typing import List

def fibonacci(n: int) -> List[int]:
    """
    Generate a list of the first `n` Fibonacci numbers.

    Args:
        n (int): The number of Fibonacci numbers to generate. Must be a non-negative integer.

    Returns:
        List[int]: A list containing the first `n` Fibonacci numbers.

    Raises:
        ValueError: If `n` is not a non-negative integer.

    Example:
        >>> fibonacci(5)
        [0, 1, 1, 2, 3]
        >>> fibonacci(10)
        [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]
    """
    if not isinstance(n, int):
        raise ValueError("Input must be an integer.")
    if n < 0:
        raise ValueError("Input must be a non-negative integer.")
    
    # Handle base cases
    if n == 0:
        return []
    elif n == 1:
        return [0]
    
    # Initialize the first two Fibonacci numbers
    fib_sequence = [0, 1]
    
    # Compute Fibonacci numbers up to the nth number
    while len(fib_sequence) < n:
        next_value = fib_sequence[-1] + fib_sequence[-2]
        fib_sequence.append(next_value)
    
    return fib_sequence

# Example usage
if __name__ == "__main__":
    try:
        num_terms = 10  # Change this value as needed
        print(fibonacci(num_terms))
    except ValueError as e:
        print(e)
