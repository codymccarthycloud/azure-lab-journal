## Implement Your First Azure AI Search Solution

### Learning Objectives
- Create an Azure AI Search service
- Import sample hotel data and configure an index
- Run queries using Search Explorer
- Understand OData syntax and field configurations
- Explore filtering, phrase search, and field selection

## Create Azure AI Search Service
- Use the provided resource group and region
- Pricing tier: Basic (not Free)
- Name the service as desired
- Confirm deployment in Azure Portal

## Import Data & Configure Index
- Use Import Data from the Azure AI Search overview
- Select sample dataset: hotels-sample from Cosmos DB
- Skip cognitive skills
- Apply suggester to HotelName field
- Leave other field settings unchanged
- Create indexer with default settings
- Confirm ~50 hotel documents are indexed

## Query the Search Index
Use Search Explorer to test queries:

Basic Search
```json
{ 
"search": "*" 
}
```
Returns all documents.


Phrase Search
```json
{
"search": "\"Santa Fe\"" 
}
```
Returns one hotel: Santa Fe Stay (located in Nashville).


Keyword Search
```json
{ 
"search": "Santa Fe" 
}
```
Returns two hotels: Santa Fe Stay and one in Santa Clara, CA.


Filter by City
```json
{ 
"search": "*", 
"filter": "Address/City eq 'Redmond'" 
}
Returns two hotels in Redmond.
```

Filter + Field Selection
```json
{
  "search": "*",
  "filter": "Address/City eq 'Redmond'",
  "select": "HotelName, Address/City, Description"
}
```
Returns only the selected fields for Redmond hotels.


### Demo App
- Use the Create Demo App feature to test the suggester
- Try type-ahead search on cities or hotel names

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/9d304587-2ea0-433c-b326-29163c9aa514)
![2](https://github.com/user-attachments/assets/f45a4303-e0d9-41ad-9cc9-c2bab9a2c9d4)
![3](https://github.com/user-attachments/assets/f220c263-9b09-4d80-80cf-cf2c91a806bf)
![4](https://github.com/user-attachments/assets/e0f9877a-acb4-4a6c-ba37-24c92c88e805)
![5](https://github.com/user-attachments/assets/15f9cbb5-4c51-4c2b-ae42-49ccc061ec1e)
![6](https://github.com/user-attachments/assets/79aa309f-1573-426b-9783-112a04e3781a)
![7](https://github.com/user-attachments/assets/3f9f4026-5c93-44b5-97ed-b3b74e9d5168)
![8](https://github.com/user-attachments/assets/43226945-525b-4682-9b37-992505588b69)
![9](https://github.com/user-attachments/assets/1e2395dc-8bb1-41bf-be06-f1deb7286aa5)
![10](https://github.com/user-attachments/assets/59682fa9-93d9-47b6-beb0-a84891802371)
![11](https://github.com/user-attachments/assets/465d6eb2-4dce-4862-8c15-92ee874f409d)
![12](https://github.com/user-attachments/assets/5300781d-a23d-41e2-9fcf-9b1149a42e47)
![13](https://github.com/user-attachments/assets/d4c9a6b5-d90e-4597-88f2-367c22739048)
![14](https://github.com/user-attachments/assets/458f58b4-a30a-4491-b1d1-17ea01ed77dd)
![15](https://github.com/user-attachments/assets/71ee685d-80ce-4515-9686-5cf724775ceb)
![16](https://github.com/user-attachments/assets/c6ef1120-f7b2-480e-b969-0020446b0e21)
![17](https://github.com/user-attachments/assets/6463e806-01c4-4956-9849-8a1c0ba57170)
![18](https://github.com/user-attachments/assets/78fb90a6-3716-4a7b-a9d4-6c68a861eb49)
![19](https://github.com/user-attachments/assets/1233a4f4-495b-483a-a70c-630f0808290b)
![20](https://github.com/user-attachments/assets/6f1b1473-3690-4c6e-8c55-50a7c136f67e)
![21](https://github.com/user-attachments/assets/83e836f9-c035-41ad-b8c0-120c5536672a)
![22](https://github.com/user-attachments/assets/25b6b404-670b-48a0-a22f-942ff43c73be)
![23](https://github.com/user-attachments/assets/3cd6622b-7084-4442-b23c-11a7399641e3)
![24](https://github.com/user-attachments/assets/5eb818f3-57ff-443a-991b-89cdfc4f1046)
![25](https://github.com/user-attachments/assets/ba91a542-1d60-485f-b442-2b6332dc5bfa)
![26](https://github.com/user-attachments/assets/861b0bf9-c3fc-4625-9243-b7405048fed2)
![27](https://github.com/user-attachments/assets/86204f8c-09b2-4a6d-a775-5fa3b8b7b4c6)
![28](https://github.com/user-attachments/assets/72d70480-854f-42e9-ba9e-dd891d5c1669)
![29 AI Search Demo App](https://github.com/user-attachments/assets/ef5dcad1-d5ea-409c-b566-80067a0d7762)


