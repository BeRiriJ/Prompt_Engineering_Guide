# Prompt Engineering Guide

https://www.promptingguide.ai/

## Examples

### Use Separators 

```
### Instruction ###
Translate the text below to Spanish:
Text: "hello!"
```

### Output Format

```
Extract the name of places in the following text. 
Desired format:
Place: <comma_separated_list_of_places>
Input: "Although these developments are encouraging to researchers, much is still a mystery. “We often have a black box between the brain and the effect we see in the periphery,” says Henrique Veiga-Fernandes, a neuroimmunologist at the Champalimaud Centre for the Unknown in Lisbon. “If we want to use it in the therapeutic context, we actually need to understand the mechanism.“"
```

### Difficulty Level

```
Use 2-3 sentences to explain the concept of prompt engineering to a high school student.
```

### Avoid Saying Something

#### For developers

```
The following is an agent that recommends movies to a customer. The agent is responsible to recommend a movie from the top global trending movies. It should refrain from asking users for their preferences and avoid asking for personal information. If the agent doesn't have a movie to recommend, it should respond "Sorry, couldn't find a movie to recommend today.".

Customer: Please recommend a movie based on my interests.
Agent:
```

Avoid saying something + tell the bot how to answer.

#### For users

```
Answer the question based on the context below. Keep the answer short and concise. Respond "Unsure about answer" if not sure about the answer.
Context: Teplizumab traces its roots to a New Jersey drug company called Ortho Pharmaceutical. There, scientists generated an early version of the antibody, dubbed OKT3. Originally sourced from mice, the molecule was able to bind to the surface of T cells and limit their cell-killing potential. In 1986, it was approved to help prevent organ rejection after kidney transplants, making it the first therapeutic antibody allowed for human use.
Question: What was OKT3 originally sourced from?
Answer:
```

### Code Generation

#### Write code

```
/*
Ask the user for their name and say "Hello"
*/
```

#### Write SQL

```
"""
Table departments, columns = [DepartmentId, DepartmentName]
Table students, columns = [DepartmentId, StudentId, StudentName]
Create a MySQL query for all students in the Computer Science Department
"""
```

## Techniques

### Zero-shot Prompting 

Like unsupervised learning

### Few-shot Prompting 

Like supervised learning

```
An example of ... is:
```

If the tasks need reasoning steps like doing math, Few-shot Prompting may not work. In these cases, Chain-of-Thought Prompting (CoT) might help.

### Chain-of-Thought Prompting (CoT)

Providing the specific '''reasoning steps''' while giving examples.

```
Q: Roger has 5 tennis balls. He buys 2 more cans of tennis balls. Each can has 3 tennis balls. How many tennis balls does he have now？

A: '''Roger started with 5 balls. 2 cans of 3 tennis balls each is 6 tennis balls. 5+ 6 = 11. '''The answer is 11.
```

### Zero-shot-CoT

Use a more generalized saying to ask the LLM to do reasoning steps, by saying *'''Let's think step by step.'''* .

```
Q: A juggler can juggle 16 balls. Half of the balls are golf balls， and half of the golf balls are blue. How many blue golf balls are there？ 
A: Let's think step by step.
```



## Basic Settings

### Temperatrue

Increasing temperature could lead to more randomness, which encourages more diverse or creative outputs.

### Top P

If you are looking for exact and factual answers keep this low. If you are looking for more diverse responses, increase to a higher value.

The general recommendation is to alter temperature **or** Top P but not both.

### Max Length

