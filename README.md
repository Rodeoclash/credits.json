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
  client: {
    client: "todo"
  },
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

Let's explore the format in a bit more detail:

### Version

```
version: "0.1"
```

The credits.json format is versioned, at the moment we are arbitrarily at version 0.1. We will freeze the standard at 1.0 then begin work on version 2.0 when needed. 

### Organisations

```
{
  name: "The Super Design Agency",
  location: "123 Street, My City, A Country",
  homepage: "http://www.example.com",
}
```

Two top level entities are allowed in the format, the first os which is Organisations. These represent the business entities that worked on the site.

## More resources

* credits.json generator coming soon
* site portfolio website coming soon