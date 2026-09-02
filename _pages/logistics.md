---
layout: page
permalink: /logistics/
title: Logistics
---

# CPSC 4880/5880: Frontier AI Models (Fall 2026)

**Architectures, Training, and Agentic Systems**

- **Instructor:** Arman Cohan
- **Meeting time:** Monday and Wednesday, 2:35 to 3:50 p.m.
- **Announcements and course materials:** Canvas and email
- **Questions and course logistics:** Ed Discussion. Graded work will not be submitted there.

The university calendar designates Friday, September 4 as a Monday class day.

---

## Course overview

Frontier AI model development involves building, training, and deploying models as components of systems that achieve state-of-the-art capabilities. This course examines the design choices that shape model architectures and training pipelines, including pretraining and post-training. It also covers reasoning models, inference-time computation, and the ways models are harnessed into agents.

Given the fast pace of the field, the course schedule and readings are subject to change with at least 10 days' notice.

This year, the course is organized around three themes:

Before the three main themes, an introductory unit will review the modern language-modeling pipeline, core transformer concepts, and common evaluation practices. This unit will establish a shared vocabulary and identify the assumptions on which later topics build.

1. **Theme 1: Frontier LLM architectures.** The modern decoder stack, mixture-of-experts, attention alternatives such as state-space and hybrid models, long context, and multimodal integration.
2. **Theme 2: Training and post-training.** Data curation, training algorithms, open training recipes, on-policy distillation, reinforcement learning with verifiable rewards, and inference-time computation.
3. **Theme 3: Agents and harnesses.** Tool use, harness and scaffold design, coding and computer-use agents, agent evaluation, reinforcement learning for agents, and agent safety.

By the end of the course, students should be able to:

- Explain the architectural and systems choices behind contemporary frontier models.
- Compare major approaches to pretraining, post-training, and inference-time computation.
- Read a recent paper critically and understand its strengths and limitations.
- Identify how tools, memory, prompts, context management, and evaluation design affect an agent's behavior.
- Connect results across papers that use different models, datasets, compute budgets, and evaluation protocols.
- Design and communicate a focused empirical study of a frontier-model technique or system.
- Carry out an AI research project.

### Format

Each theme opens with one or two instructor-led lectures that establish the foundations and describe the current research landscape. We will then examine important papers in greater depth through student presentations and class discussion. At the end of each paper-presentation session, students will participate in small-group discussions about the papers presented.

**Guest lectures.** We will also invite researchers from leading academic and industry AI labs to discuss cutting-edge topics.

The course will not have separate coding or hands-on assignments. Instead, students will complete a final project with milestones throughout the semester.

#### Structure of paper discussion sessions

The tentative structure of the paper presentation and discussion sessions will be as follows:

<div class="table-scroll" markdown="1">

| Component             | Approximate time                         |
| --------------------- | ---------------------------------------- |
| Introduction and optional quiz | 5 minutes                       |
| Paper presentation 1  | 25 minutes (20-minute presentation + 5-minute Q&A) |
| Paper presentation 2  | 25 minutes (20-minute presentation + 5-minute Q&A) |
| Group discussion      | 15 to 20 minutes (10 to 15 minutes of discussion + 5-minute synthesis) |

</div>

## Grading

The course grading components are listed below:

<div class="table-scroll table-scroll-wide" markdown="1">

| Component                     | Weight | Notes                                                        |
| ----------------------------- | ------ | ------------------------------------------------------------ |
| Prerequisite assignment       | 1%     | A self-assessment that will help students and the course staff evaluate whether students have the necessary background. |
| Participation and discussions | 24%    | In-class discussions, quizzes, and group worksheets. |
| Paper reviews                 | 15%    | A short structured review, approximately one page, submitted before each student-led session. |
| Paper presentation            | 15%    | Teams of four. Each team presents one paper in a 25-minute slot that includes Q&A. Two teams present per session. Teams submit two candidate takeaway prompts with their slides. <br />Rubric: technical accuracy 25, clarity 15, overall presentation quality 25, critique 15, prompts and Q&A 10, time management 10. |
| Midterm                       | 20%    | An in-class, closed-book midterm covering lectures and required papers. |
| Final project                 | 25%    | Teams of up to four students. |

</div>

### Participation

Participation includes in-class group discussions, constructive engagement, questions, and the quality of group worksheets. Quality and preparation matter more than how often a student speaks. Because opportunities to speak in a large class are uneven, students do not earn or lose participation credit simply because they are invited to answer a question.

#### Quizzes

Approximately four sessions will include a short in-class quiz about the papers being presented that day.

#### Group discussion

After the paper presentations, students will divide into groups. Each group will be randomly assigned one of the two papers. Group members will discuss what they learned and develop a critique of the paper.

Each group will then submit a handwritten report summarizing its discussion. The prompt may ask students to explain the paper's central method, compare it with another work, discuss an important result, identify an unconvincing claim or execution flaw, or describe a meaningful limitation. We may ask one or two groups to share their conclusions with the class.

Group discussions aren't necessarily limited to paper presentations. They can also happen during regular lectures.

#### Missing sessions

We understand that students may occasionally need to miss class. Everyone may miss up to **three sessions** without losing participation points. This flexibility does not apply to a student's presentation day or the midterm. If you anticipate a recurring scheduling conflict or expect to miss more than three sessions, we strongly advise against taking the course.

### Paper reviews

By **12 p.m. on the day of each paper-presentation session**, every student except the presenters must submit a short structured review of the papers assigned for that session. We will provide a template.

### Paper presentation

Students will present in groups assigned by the course staff. Due to the size of the class, we will have limited flexibility to reassign students or move them between groups. We will begin making group assignments once enrollment stabilizes.

The presentation grade will reflect both the team's work and each student's individual contribution. Evaluation will consider technical accuracy, clarity, critical analysis, connection to the course and prior lectures, presentation quality, timing, and handling of questions.

#### Slides due the night before the presentation

Presenting teams must submit their slides by **9 p.m.** on the night before class. The teaching staff will review the slides and may request changes. Teams that submit after the deadline will not receive advance feedback.

If a teammate cannot attend the assigned presentation because of illness or another documented emergency, the remaining team members should adjust their roles. The live presentation will proceed as planned. In an approved emergency, the absent student will complete an individual makeup that may include a recorded segment and written worksheet.

### Midterm

The midterm will evaluate concepts and connections across lectures and assigned papers. It may include short explanations, comparisons of methods, interpretation of experimental results, and critiques of research methods. The format and scope will be discussed closer to the midterm date.

### Final project

The final project offers two tracks:

1. **Guided track.** The course staff provides a project topic and a defined starting point.
2. **Open track.** The team proposes its own open-ended project related to the course.

The project milestones are:

1. Team formation, in teams of up to four
2. Project proposal, 3%
3. Progress report 1, 3%
4. Progress report 2, 3%
5. Project presentation, 9%
6. Final report and project artifacts, 7%

**Proposal:** Each team will submit a one-page proposal. The proposal should state and motivate the problem and position the project within related work. It should also briefly describe the proposed approach and the experimental plan, including relevant baselines and datasets.

**Progress reports:** Each checkpoint requires a one-page report using a template provided by the course staff. We expect reasonable progress at each checkpoint. The report should explain what has been completed, what has changed since the proposal, what the early evidence suggests, and how the team will use the remaining time.

**Final presentation:** The final presentation may take the form of a talk or poster. The format will be selected after enrollment stabilizes.

**Final report:** Each team will submit a four-page report in a conference format, such as the [NeurIPS format](https://www.overleaf.com/latex/templates/neurips-2023/vstgtvjwgdng). The report should describe the project motivation, related work, approach, results, and discussion. Negative results will not be penalized when they are accompanied by careful analysis of why the methods did not work and what the findings reveal about the problem. References and appendices do not count toward the page limit.

The accompanying artifact should include clear instructions and enough documentation to evaluate or reproduce the central results when feasible. Teams will also submit a reproducibility checklist, an individual contribution statement, and the required AI-use disclosure.

Graduate students are expected to address a research question with a clear element of novelty. This may take the form of a new method, evaluation, analysis, extension, or application. Graduate project reports should also include a more substantial treatment of related work. Undergraduate projects may emphasize careful replication, controlled analysis, or system building when the scope and evaluation are appropriate.

Projects will be evaluated on the importance and clarity of the question, the quality of the experimental design, the strength of the evidence, the care of the analysis, and the transparency of the final report. Well-executed projects with negative or mixed results can receive full credit.

### Approximate grading cutoffs

For undergraduate students, final grade cutoffs will be approximately 93+ for A, 89+ for A-, 85+ for B+, 82+ for B, 78+ for B-, and so on. Graduate students are graded on the H/HP/P/F scale, with approximate thresholds of 91+ for H, 84+ for HP, and 70+ for P.

**Note:** These thresholds are intended as general guides. The instructor reserves flexibility to adjust them slightly based on the difficulty of the coursework and the overall course results.

## Use of AI tools

AI tools are not permitted for paper reviews, paper summaries, reading responses, in-class writing, or other short reports intended to demonstrate a student's understanding of assigned papers.

Current AI models can produce plausible responses to these assignments, but relying on those responses would bypass the learning objective. Important skills in AI research include understanding new concepts, reading and critiquing papers, and synthesizing findings into coherent reports.

Students are therefore expected to read the papers themselves, develop their own analysis, and write these submissions in their own words.

You may use AI tools to ask follow-up questions while studying, review prerequisite concepts, generate practice questions, or obtain another explanation of material you have already read. These uses should support your own engagement with the assigned papers and may not be used to produce graded work.

The same expectation applies to the technical content of paper presentations.

Do not ask an AI tool to generate a slide deck or presentation for you to deliver. The ability to present technical content coherently and clearly is one of the skills developed in this course. Presenting teams must read and analyze the assigned paper themselves. AI tools may be used for limited purposes such as slide formatting, accessibility checks, or rehearsal, provided that they do not generate the presentation's technical explanation or critique.

For final projects and other technical work, AI tools may be used for literature discovery, coding, debugging, and experimental analysis.

Students must read any sources they cite and take responsibility for the code they deliver. We strongly advise against **vibe coding** without careful manual control and auditing. Do not generate large pieces of code without reviewing each component, testing its behavior, and understanding what it does.

Project proposals, progress reports, and final reports must be written by the students. You may use AI tools for limited sentence-level polishing, but you may not use them to draft sections or generate substantial passages.

**Disclosure requirement:** Any permitted AI use must be disclosed in a clear statement that identifies the tools used, how they were used, and explains their role. Students remain responsible for every submitted claim, citation, result, and line of code.



## Academic integrity

[Yale's academic integrity guidance](https://catalog.yale.edu/undergraduate-regulations/regulations/academic-dishonesty/) requires students to acknowledge sources and follow the collaboration rules for each assignment. Cite papers, code, datasets, model outputs, conversations, and AI assistance that materially shape submitted work. Team submissions must include an accurate contribution statement.

Fabricated citations, altered outputs, undisclosed copied text or code, and falsified results violate course and university policy. Ask the instructor when a source or collaboration practice is unclear.

## Accessibility and inclusion

Students who need accommodations should contact Student Accessibility Services and the instructor early in the term. Presentation teams should use readable figures, define visual encodings, provide citations, and make slides available as directed. Discussion leaders share responsibility for an environment where questions, uncertainty, and respectful disagreement are welcome.

## Communication

Canvas is the source for announcements, deadlines, assignments, and grades. Ed Discussion should be used for questions and course discussions.

## Course flexibility

Frontier AI develops quickly, and this is the first offering of the course in the current format. The reading list, order of topics, guest schedule, and some implementation details may change as the semester develops. Changes will be made to improve the coherence of the course, respond to important new work, or address the practical needs of a large class.

Students will receive reasonable notice of substantive changes. A paper already assigned to a presentation team will be changed only with additional notice and consultation. Policy clarifications will be communicated with advance notice and will not retroactively reduce credit for work already completed under the earlier guidance.
