add process.md
在我的毕业设计期间，我在开发一个网页游戏，而我对代码几乎一无所知。我依赖 Claude 帮我写出大部分功能，它们确实能运行。但每当我想要做一个主观上的调整——一段过渡的节奏、一个跳跃的重量感、一个场景的氛围——我都不知道该去代码里的哪个位置找。即使 Claude 给了我一小段针对性的修改代码，我也不知道该把它粘贴到哪里，也不知道怎么把它和项目的其他部分连接起来。我唯一的选择，就是一遍又一遍地让它把整个文件从头重写，然后再运行。这既缓慢又重复，还令人沮丧。更糟的是，结果往往并不是我真正想要的，因为我只能用模糊的语言描述一种感觉，而无法精确地把它规定下来。这就是为什么我开始追问：既然在 2026 年机器已经能写出不错的代码，我为什么还要学编程？我的答案是：我要学的不仅仅是怎么写代码，更是怎么读懂和理解它——怎么让它服务于我的意图，而不是把它的默认选择强加给我。我意识到，理解，才是拥有一个作品的前提。
# PROCESS.md

I used an AI assistant (deepseek) during this essay.

## What I used it for

- Brainstorming the overall structure of the essay
- Translating and polishing my Chinese draft into English

## What I kept

I kept the AI's English rendering of my thesis sentence:  
**"Understanding, I realised, is the precondition of owning a work."**  
It was concise, and it captured exactly what I learned from my graduation project. My original Chinese version was longer and less direct; the AI helped me compress it without losing the meaning.

## What I rejected

The AI suggested starting the essay with something like:  
*"In an era of rapid technological change, AI is transforming the way we create."*  
It also proposed ending with:  
*"AI won't replace artists, but artists who use AI will replace those who don't."*  

I rejected both. They are familiar, generic lines that do not represent my argument. My point is not about competition between people and machines, nor about winners and losers. It is about the need to understand the medium in order to truly own the work. Those clichés would have weakened my position and made the essay sound like every other AI-generated reflection.


## Update (2026-09-10)

Used DeepSeek on Beattie's talk transcript.

### Used for
- Summarising key ideas and connecting them to my argument
- Polishing the new section in English

### Kept
- Beattie's Logo story; to control a machine you must understand it
- The Mandelbrot zoom as reading hidden structure in code

### Rejected
- Over-long summaries that would make the essay feel like a book report
- Generic AI-sounding transitions like "In a world of rapidly advancing AI..."
- Quotes irrelevant to my argument about reading and judging code


# PROCESS

Final update: 2026-09-13

## Today's work

- Used DeepSeek to summarise the Beattie transcript and verify the logo example before finalising the essay.
- Refined the English of the final draft, checking that each paragraph still reflected my own experience.
- Completed the final README and PROCESS.md, and prepared them for submission.
- Diagnosed and fixed a `git push` failure that had blocked submission.

## What I kept

- The main thesis: with AI writing code, understanding code is the precondition of owning a work.
- The Beattie logo example, the move from describing to specifying, code as a material, and the softened Nake/Nees conclusion.
- The verified references and the in-text link required by the assignment.

## What I rejected

- Generic AI sentences that did not match my own experience.
- Any claim about early computer art that went beyond what the source could support.
- Any unverifiable reference.

## Git push troubleshooting

- Problem: `git push` repeatedly failed with `Failed to connect to github.com:443 over proxy 127.0.0.1:7890: Connection refused`.
- Cause: leftover GitHub-specific proxy settings in the global Git config, stored as `http.https://github.com.proxy` and `https.https://github.com.proxy`. Removing the general `http.proxy` did not affect them.
- Fix: found the entries with `git config --list --show-origin | findstr proxy`, then removed them with:
  - `git config --global --unset http.https://github.com.proxy`
  - `git config --global --unset https.https://github.com.proxy`
- Result: `git push` succeeded; the remote repository now contains the final README and PROCESS.md.
- What I kept: the HTTPS remote URL and a clean proxy-free Git configuration.
- What I rejected: force-pushing, switching to SSH, or disabling all proxy settings globally when only the two GitHub-specific entries were the problem.