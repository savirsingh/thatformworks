# Thatformworks
### Make your HTML form work for free!

Create a pull request and add your mail function/route to app.py and I will merge it!

Form actions will be https://thatformworks.pythonanywhere.com/mailNAMEHERE.
Be sure to add method="POST" in your form too!

Thatformworks is recommended for ALL HTML forms, including contact and reservation forms.

Blog Post About Thatformworks: https://savirsingh.github.io/blog/01

Example function/route:
```
# mail function for (ADD YOUR NAME/GITHUB USERNAME HERE)
@app.route("/mailNAME", methods=["POST"]) # change NAME to your name or GitHub username
def mailNAME(): # again, change NAME to your name or GitHub username
    email = request.form["address"] # look at next comment
    message = request.form["important"] # the request.forms shouldn't be changed
    EMAIL_ADDRESS = 'THEEMAIL' # don't change this
    EMAIL_PASSWORD = 'THEPASSWORD' # don't change this either - they're both for me to look after
    
    msg = EmailMessage() # leave as is
    msg['Subject'] = (email) # leave as is again
    msg['From'] = EMAIL_ADDRESS # again, leave as is
    msg['To'] = 'your_email' # here, add YOUR EMAIL ADDRESS, the one you want to receive messages at
    
    # change nothing from here!

    msg.set_content(message)

    with smtplib.SMTP_SSL('smtp.gmail.com', 465) as smtp:
        smtp.login(EMAIL_ADDRESS, EMAIL_PASSWORD)
        smtp.send_message(msg)

    return redirect("/success")
```
THIS IS ONLY AN EXAMPLE, YOUR NEEDS MAY BE DIFFERENT (E.G. YOU MIGHT NEED 3 REQUEST.FORMS INSTEAD OF 2). CHANGE ACCORDING TO WHAT YOU NEED.

Example HTML form (after creating function/route in app.py):
```
<form action="https://thatformworks.pythonanywhere.com/mailYOURNAME" method="POST">
    <input type="text" name="RELEVANT NAME GOES HERE">
    <input type="email" name="RELEVANT NAME GOES HERE">
    <input type="submit" value="SUBMIT">
</form>
```
AGAIN, THIS IS ANOTHER EXAMPLE. YOUR FORM MAY LOOK SLIGHTLY DIFFERENT.

Fork it and add your mail function/route. Create a pull request afterwards. I will merge it, and then you can then use it for your form action in HTML.

I made this for my own forms, but if anyone else needs this, they are free to create a pull request for their own form (instructions above).

I've hosted the production version of Thatformworks on PythonAnywhere.

Just to be clear:
You CANNOT redistribute, modify, or use this software/code in any way. You may only create and merge pull requests and suggest edits to it. You may use form actions which are defined in the app.py program (using the thatformworks.pythonanywhere.com subdomain).
