# Readers-Writers-Starve-Free-Solution
Pseudocode for starve free solution to readers-writers problem

Explanation:

In this solution, readers and writers both wait in a turnstile to ensure that a fair number of readers and writers get access to the shared resource. The count variable keeps track of the number of readers currently reading. The mutex semaphore is used to protect the count variable.

When a reader arrives, it waits in the turnstile and acquires the mutex to increment the count variable. If it is the first reader, it waits for the roomEmpty semaphore to indicate that the writing room is empty. Once it has finished reading, it decrements the count variable and checks if it is the last reader. If so, it signals the roomEmpty semaphore to indicate that the writing room is empty.

When a writer arrives, it waits in the turnstile until the roomEmpty semaphore indicates that the writing room is empty. It then signals the turnstile to allow more readers and writers to access the shared resource. Once it has finished writing, it signals the roomEmpty semaphore to indicate that the writing room is empty.

This solution ensures that readers and writers get access to the shared resource in a fair and starve-free manner.
