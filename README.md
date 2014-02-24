# credits.json

Machine readable data format that describes the creators of a website.

## Wait a minute, isn't this humans.txt?

Not quite. Humans.txt is a great effort but it's not easily machine parsable, in fact, being easily machine parsable defeats the purpose of humans.txt (that is, making it easy for humans to read!).

## Ok, but why?

With a credits.json file it makes it easy to track what websites you've built over the internet. These could be websites you've built for a client, websites you've built working for an organsation or websites you've freelanced or contracted on. Think of adding a credits.json as putting an entry into a database of your portfolio.

## Who's making this? Who's in control of it?

At the moment it's just two of us but the purpose of creating this repository is to get input from everyone on what the credits.json format should include. If you've got some ideas or suggestions, please fork, implement and make a pull request so everyone can discuss the changes.

## Ok, show me what it looks like

```
{
  version: "0.1",
  organisations: [
    {
      name: "The Super Design Agency",
      location: "123 Street, My City, A Country",
      homepage: "http://www.example.com",
      people: [
        {
          name: "John Doe",
          email: "$2a$10$JGDDOBPPnuUiwb/OSHL4du9NwbHb/ZygFJm/SXk/wl1b9NoxlHQAO",
          roles: ['Design', 'Front end development'],
          location: "123 Street, My City, A Country",
          homepage: "http://www.example.com"
        }
      ]
    }
  ],
  people: [
    {
      name: "Jane Doe",
      email: "$2a$10$Rs2//C.zRkfYeXiZwp.vuutbkKV6mxR5Xnpo8D/oShsrj9VTIf/Mm",
      roles: ['Backend end development'],
      location: "123 Street, My City, A Country",
      homepage: "http://www.example.com"
    }
  ]
}
```

Ok, some notes on the format.

* Note that the email addressed is hashed using bcrypt, this means you can keep a consistent email id for the different sites you've worked on without incurring spam.

## More resources

* credits.json generator coming soon
* site portfolio website coming soon