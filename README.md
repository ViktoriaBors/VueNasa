# Vue Nasa Image
## Practice project for Vue learning

### **_Introduction_**
Learning Vue is still going strong. I think smaller projects are perfect to practice alone and get confident about the technology. 

I found free api on the Nasa site, to search images and other cool things.
### **_Used Technologies_**
1. Vue Js
2. Tailwind Css
3. Nasa free api

**Aim of the Project**
It is a practice mini project to get more hands-on experience with Vue. The user can pick a date to see that day's image and other events.

**Challenges within the Project**

 **Day 1**
 
 My first problem was with select date. I wanted to block any future date to be selected. But today's date is always changing so I could not hardcoded the max attribute value in the input (type="date").

 So first I used new Date(Date.now()) - which gives back a string. This string is not the same format what the date-picker accepts as a max value. I needed to re-computed (re-formatted) to the acceptable string. I found that toISOString() - make the right format but some extras on the end what I cut off with slice. So now the format was the same format what is acceptable.

 Next problem was that I messed up how to bind data. I wanted to use the {{}} format for an attribute - which obviously did not work. The I realized that for attribute binding I need to use :attribute="" form. And voila worked.

 **Day 2**

 So select date max-value actually working :) Jee. I made it pretty simple the whole app. So if here was no submit then I hide the image container where I want the requested data/img to come. After submit the condition changing and the form is hidden. So I used v-if solution for this.
## **_What have I learned_**
Vue - data binding (attributum) and v-if

## Deployed: 2022. October
