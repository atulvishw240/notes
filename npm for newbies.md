- intro
- two approaches to use third party packages in our code.
- package.json file
- useful commands and what they do

## Introduction

>Let me first try to convince you, why would you want to use third-party packages in your applications instead of re-implementing these existing solutions by your own.

In software engineering much emphasis is given on "code quality" and "code reusability" and for a good reason. If your code is **reusable** then it can be used in new contexts to solve different problems, that's the goal of **abstraction**. Solve a small problem, provide a nice interface to your solution, so other people could use your smaller solution to solve their own bigger problems.

https://x.com/ID_AA_Carmack/status/1258531455220609025
The best example that I can think of is **FFmpeg**. It was created 25 years ago and still today almost all companies that has to do anything with audio and video uses FFmpeg in their backend. You can only imagine how much time, money and effort it will cost to design a system like FFmpeg that even most of the **MAANG** companies rely on FFmpeg, instead of recreating their own version of FFmpeg.

As you build more complex applications you may not want to write everything from scratch as it will lead to ton of wasted effort . Why rewrite your next AI-powered IDE from scratch, when you can just fork VS Code and build on top of it. It saves you both time and money.

>Convinced now? Let's move on to how would we use third-party packages in JavaScript ecosystem.

## Ways to use third party packages in our apps

There are mainly two ways to use third party packages in your apps:
1. Download the third-party code and link it your app
2. Use a package manager

### 1. Download third party code



