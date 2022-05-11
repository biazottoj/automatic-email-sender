# Email sender

This repo contains a small python script to send emails automatically from your personal/work email account.
Note, that I did not test this script after migrating it into a separate repository.
So there might be some errors :(, but it's a pretty straightforward script so it should be easy to fix.

## Usage
The first thing you need to do is to configure the `data/login.secret` file.
This files contains the authentication credentials to connect to your email provider.
The file **must contain two lines only**, the first line is the **username**, and the second line is the **password**!
Most services (Google included) require you first create an "App password", a special token that will act as your password.
This can be easily created from your account web page (for Google, visit [here](https://support.google.com/mail/answer/185833?hl=en) for more info).
Therefore, in the `login.secret` file you will need to put your username and then the app password.

```shell script
# Provides CLI support to execute the script
pip install fire

# Show help
python main.py send_emails

# Executes the script
python main.py send_emails data/contacts.csv data/email-template.txt data/login.secret "Your Name" "The Subject" --dry-run
```
Remove `--dry-run` when you are ready to send the emails for real.

Note that, by default, this script is configured to work with Google emails.
You can easily change that by changing the SMTP server through the `--email_server_smtp_address` and `--email_server_smtp_port` parameters.
