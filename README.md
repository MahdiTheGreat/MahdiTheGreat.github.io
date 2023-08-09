# Mr or Mrs?

One of the most difficult tasks in class, especially online classes, is the correct use of Mr. and Mrs. prefixes. For example, you see Mahdi Afarideh's name in the list and you don't know whether you should say Mr. Afarideh or Mrs. Afarideh. In this project, we plan to design a website that will help teachers in this important matter. 

In this site, there are two general situations, one when the user knows the gender of the name and wants to save it on the site and two when the user does not know and wants to find out through our site.

In the website a background covers the whole page, and in the middle of it is a transparent rectangle. We are careful so that the transparency is not so high that the text inside the rectangle cannot be read. The middle rectangle contains all your displayable content. This rectangle is only the size of it's contents, but to display it more beautifully, we use padding. The content consists of two parts that are placed horizontally next to each other. The first part is a form that consists of two entries. The first entry is in text form and it can be done if one already knows the answer. The second input is in the form of two radio buttons that allow the user to enter the desired name, enter it and this answer is saved for the future. The design spec of this website can be seen below:

![image](https://github.com/MahdiTheGreat/MahdiTheGreat.github.io/assets/47212121/d9608df4-430c-4842-a159-559435748f00)

and the implemenation is shown below:

![Screenshot 2023-08-09 at 11-00-19 Mr  or Ms](https://github.com/MahdiTheGreat/Mr-or-Mrs/assets/47212121/351fc0e2-9d69-42df-a51a-485bafe3a1ce)

After filling out the form, the user clicks on submit button and his request will be sent. For example below we fill the form with the name Xena:

![Screenshot 2023-08-09 at 15-35-10 Mr  or Ms](https://github.com/MahdiTheGreat/mahdithegreat.github.io/assets/47212121/b44fae2a-171b-4e7b-b77a-9b3799874db9)

We consider the following in the implementation of the input form:

• The inputed name should have a maximum of 255 characters. 
• The name entered by the user must consist only of spaces, upper and lowercase English letters.
• The submit button should not perform the default behavior of the browser.

We use the following website to predict the gender of the given name:
https://api.genderize.io/?name=Xena
in the above link, the inputed name is Xena and the request is done as a GET and the inputed name is used as a query string. The output of this request is as follows:

{
"name":"Xena",
"gender":"Female",
"probability":0.96,
"count":49197
}

And therefore needs to be converted to an object in javascript. Error is also handled and shown on the website. 
The error could be because of the inability of the api to guess the gender or connection issues. The output on the website can be seen below:

![Screenshot 2023-08-09 at 15-34-41 Mr  or Ms](https://github.com/MahdiTheGreat/mahdithegreat.github.io/assets/47212121/eeacddb3-50ea-48d2-9422-63473413f9d6)

# Saved answers

There are times when the website makes a wrong prediction, in which case you can get the correct answer by asking the student and manually enter the gender for the name, like below:

![Screenshot 2023-08-09 at 15-48-34 Mr  or Ms](https://github.com/MahdiTheGreat/mahdithegreat.github.io/assets/47212121/dc46d7c7-be26-4f2b-8a33-e2b1c2510215)

In this case, this website has the ability to store the correct answer. if a stored answer is available for the entered name, the the stored answer is displayed to the user, like below:

![Screenshot 2023-08-09 at 15-35-28 Mr  or Ms](https://github.com/MahdiTheGreat/mahdithegreat.github.io/assets/47212121/7f3353fb-8481-4f58-9a17-a3793e3685ff)

If a gender has been already stored for a name and the user gives another gender, the previous value will be deleted, like below:

![Screenshot 2023-08-09 at 15-50-31 Mr  or Ms](https://github.com/MahdiTheGreat/mahdithegreat.github.io/assets/47212121/c2ab3b91-17e4-42e9-92e5-977adbe135a5)

As we can see below, the stored answer has changed to male.

![Screenshot 2023-08-09 at 15-50-42 Mr  or Ms](https://github.com/MahdiTheGreat/mahdithegreat.github.io/assets/47212121/cc514bad-6584-4298-a668-cf150c17af99)

If the user wants to delete the saved value for a name, after sending a request for that name, he can use the delete button that is displayed in the saved answers section. Notice that the saved answers section will only be displayed if there is a saved answer.

# step by step

We want to review the procedure of working with this website step by step. In this section:

scenario one:
1. The user wants to find the gender of the name "Xena".
2. The user enters the name "Xena" in the specified field and prediction is done.
3. The prediction result will be displayed to him and he can save it if necessary

scenario two:
1. The user wants to find the gender of the name "Xena", but predicts that this name is male.
2. The user enters the name "Xena" in the specified field and prediction is done.
3. The prediction result is displayed to the user, but the user prefers to use his knowledge and save the male gender for this name.
   
scenario three:
1. The user wants to find the gender of the name "Xena", but he already entered this name and saved the result.
2. The user enters the name "Xena" in the specified field and prediction is done.
3. The prediction result is displayed to the user, next to it it is stated that the result is already saved for this name.
4. The user can change the saved result or delete it.









