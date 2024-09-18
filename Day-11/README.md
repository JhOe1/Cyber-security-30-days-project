# SOC Analyst Challenge - Day 11

## Topic: Brute Force Attacks

### Objective:
Today's focus is on understanding the fundamentals of Brute Force attacks, their variations, and how to defend against them. This is an essential attack method that every SOC analyst must be familiar with due to its prevalence in real-world environments.

### What is a Brute Force Attack?
A brute force attack occurs when an attacker attempts to gain unauthorized access to an account by systematically trying various password combinations until the correct one is found. This method is as simple as it is effective, especially when paired with automated tools that can quickly cycle through combinations. 

### Common Variants of Brute Force Attacks:
1. **Simple Brute Force Attack**: The attacker tests every possible password combination.
2. **Dictionary Attack**: Instead of random combinations, the attacker uses a pre-compiled list of commonly used passwords, phrases, or words.
3. **Credential Stuffing**: Attackers use credentials obtained from previous breaches, testing username-password pairs to gain access.

### Defense Strategies:
To defend against brute force attacks, I explored three common strategies:
1. **Longer Passwords/Passphrases**: Using passwords of at least 15 characters that include a mix of letters, numbers, and symbols makes brute force attacks significantly harder to succeed.
2. **Multi-Factor Authentication (MFA)**: This adds an extra layer of security, requiring additional verification beyond a password, such as an SMS code or an authenticator app.
3. **Vigilance**: Being cautious with unexpected login requests and regularly monitoring whether your account has been exposed in data breaches (e.g., through services like *Have I Been Pwned*).

### Tools Used in Brute Force Attacks:
1. **Hydra**
2. **Hashcat**
3. **John the Ripper**

These are some of the most popular tools used for brute force attacks, particularly for ethical hacking and security research purposes. In the course of today's challenge, I reviewed how these tools are employed to exploit vulnerable accounts and how defenders can recognize such activity.

### Conclusion:
Understanding brute force attacks and their variants is critical for defending against unauthorized access. As part of today’s exercise, I deepened my understanding of how these attacks operate and explored ways to effectively protect against them. This knowledge is crucial for every SOC analyst to stay ahead of potential threats.

