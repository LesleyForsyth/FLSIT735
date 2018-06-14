# Tor is good, but...

Those concerned about privacy and anonymity ought to understand that both are remarkably hard to achieve.


## A lesson from Harvard Bomb Hoax

In 2013 a Harvard student emailed a bomb threat, supposedly to postpone a final exam. And he succeeded. Students and staff were warned to evacuate the university premises, shutting down the university for a while. 

Of course, the student took precautions and hided his email address and IP address. The IP address can be hidden with, guess who, Tor. The email address 
was a temporal and anonymous address obtained from the free program *Guerrilla Mail*. 

So how did the FBI found that the bomb threat came from Eldo Kim? 

It was clear that the hoaxer was using an anonymiser, like Tor. And the hypothesis that he/she was a Harvard student. The trick is that Tor can anonymize your connections, but you need to connect to Tor in first place. Luckily for the FBI, Eldo Kim connected to Tor through the university network. The network system administrator only had to see who connected to public Tor nodes on that day. And it happened that a few connections where made, narrowing down the list of suspects to a few users. The rest was easy. Harvard computers can only be used if you enter a correct email address and password, and Voilá! 

## The power of metadata 

Metadata is data about other data, or information about other information. Sounds tricky? That's because it is. Is an IP address data or metadata?

Let's ask an easier question: is the content of your message data or metadata? We better say it is just data, because is *the* data you want to send. An IP address, instead, is not part of the main content, so it may be considered data, but metadata. 

Computer applications generate and use a plethora of data that, although are not essential, improve their services. Does Facebook needs to know the duration of your connection to provide the service of a social network? It doesn't. But this information helps them to predict content that is interesting or uninteresting for you. Facebook also collects how often you log in; the people, pages, and hashtags you interact with; and even your mouse movements.

Tor cannot prevent application from learning metadata. For example, we could send an encrypted message through facebook as we did in the first Week, so Facebook won't has access to *the data*. We can even use Tor to hide from facebook our IP address. 
However, Facebook still know who are we sending to this message, when, etc.

## Your task

Now that you know the limitations of an IP anonymiser like Tor, I want you to discuss how do you think we can prevent applications from collecting metadata. 