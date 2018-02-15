# FancyBookUtil
an util for bukkit to create written books

//create book:
FancyBook book = new FancyBook("title", "author");

//create page: you can choose between these
FancyTextComponent text = fancyTextComponent("text", ChatColor.GREEN, "bold");
FancyTextComponent text = new FancyTextComponent("text", "green");

//there are 5 attributes: "bold", "italic", "underlined", "strikethrough" and "obfuscated"

//create hover event: you can add lines by using .addText(FancyTextComponent)
FancyHoverEvent hEvent = fancyHoverEvent(fancyTextComponent("hover text", "red", "italic"));
hEvent.addText(fancyTextComponent("\nmoew hover text", ChatColor.BLUE));

//create click event:
FancyClickEvent cEvent = fancyClickEvent(runCommand, "/help");

//add text to page:
page.addText(text);
page.addText(fancyTextComponent("hoverEvent", "blue", hEvent));
page.addText(fancyTextComponent("clickEvent", "red", cEvent));

//create new page
FancyBookPage page2 = new FancyBookPage();

//add text to page 2
page2.addText(fancyTextComponent("new page :D", ChatColor.DARK_AQUA, fancyClickEvent(runCommand, "/help"), fancyHoverEvent(fancyTextComponent("/help"))));

//add pages to book
book.addPage(page, page2);

//print json book to console
System.out.println(book.translateBook());

//open book for player
book.openBook(player);


//book.translateBook() returns the json for your made book
//book.openBook(Player) opens the book