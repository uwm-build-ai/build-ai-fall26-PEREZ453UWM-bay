👋 Welcome to Campfire

```sql
SELECT * FROM projects WHERE id = 'gig_board'
```
{: .query bind="projects" #my_project }

**{= my_project.first.name }** — {= my_project.first.story }

I chose this project because I’m already building Campfire for my senior capstone. Campfire is a project management system with a quest theme, where larger projects are campaigns and smaller tasks are quests. Employees can track their progress and complete checkpoints that a project manager approves. That made me think, why not take that idea and make something for freelance workers?

My aim: Both money and social impact. I want to help freelancers earn money and build experience while helping people and small businesses find workers with the skills they need.

My twist: For this app, I want to make an adventurer’s quest board for freelance work. People and businesses could post jobs as quests, showing the required skills, deadline, and payment as the reward. Freelancers could browse available quests, apply for work that matches their skills, and build a profile showing the quests they’ve completed.