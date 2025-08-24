## Chatting with a Bot Using Azure Cognitive Services for Language

### Summary

Your goal is to build a bot that answers customer questions using a custom knowledge base:
- Create a custom question answering project
- Import an FAQ document from GitHub
- Add alternate phrasings to questions
- Test the bot’s responses in Language Studio

## Step-by-Step Instructions

- Log In to Azure Portal and Language Studio
- Use lab credentials in an incognito browser window.
- Navigate to the Language resource in Azure.
- Click Get started with Language Studio.
- Sign in again inside Language Studio.
- Select the only available Azure directory, subscription, and language resource.

Note: Resource name population may be buggy—refresh the page if needed.

## Create a Knowledge Base from an FAQ Document
In Language Studio, click Create new → Custom question answering.

- Name your project: GreeneryFAQ
- Add source:
- Click +Add source → URLs
- Use this URL:
(Code)
- https://github.com/ACloudGuru/content-AI-900/blob/main/4-greenery_FAQ.xlsx?raw=true
Click Add all to import the FAQ.

## Add Alternate Questions

- Click the imported source to view Q&A pairs.
- Select: What is your return policy?
- Click +Add alternate question → Type: Returns?
- Save your changes.

## Test the Bot

- Click Test in the top menu.
- Ask: Returns? → Response: We do not accept returns for our plants.
- Ask: Why is our order late? → Response: Steve, the summer intern, is working on it.

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/4116aeed-30e2-4dd0-ac77-6f48549d2757)
![2](https://github.com/user-attachments/assets/c2385a72-2fde-433b-a7d5-776e9e9d8c74)
![3](https://github.com/user-attachments/assets/2887585b-be30-4e39-9db3-e6a76c02d2be)
![4](https://github.com/user-attachments/assets/e754c242-6d81-431f-afdc-0de7740ea72a)
![5](https://github.com/user-attachments/assets/b4b4058b-22b8-42ef-bfaf-e055f27812fe)
![6](https://github.com/user-attachments/assets/0864f013-f7d0-4b3c-9c62-6f4c15ced2e7)
![7](https://github.com/user-attachments/assets/32704689-1afc-45d3-8143-93ba06f1c747)
![8](https://github.com/user-attachments/assets/e9d5c01c-4886-4388-b58d-7ce6433970b8)
![9](https://github.com/user-attachments/assets/d89bed9c-80f3-4071-ad8e-94c9cf476ef4)
![10](https://github.com/user-attachments/assets/4eeb6a62-d4ad-43ea-b557-c87c1c48465e)
![11](https://github.com/user-attachments/assets/310dae08-bb17-4ad6-9067-1d8187f7f5ed)
![12](https://github.com/user-attachments/assets/620fa0ab-433d-4340-add1-52a5b267fc14)
![13](https://github.com/user-attachments/assets/65aaede6-9f14-4ec1-90ff-81fdb8cdd34e)
![14](https://github.com/user-attachments/assets/6e2113ff-6fb8-4ea4-90d1-eb59d6a2b57f)
![15](https://github.com/user-attachments/assets/0b774746-202e-49c8-b47c-d0464aa09183)
