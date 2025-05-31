Prince Khand Thakuri
Title of Thesis
Metropolia University of Applied Sciences
Bachelor of Engineering
Electronics Engineering
Bachelor’s Thesis
25 May 2025 
Abstract
Author:	Prince Khand Thakuri
Title:	Title of the Thesis
Number of Pages:	xx pages + x appendices
Date:	1 March 2021
Degree:	Bachelor of Engineering
Degree Programme:	Name of the degree programme
Professional Major:	Name of the professional major
Supervisors:	First name Last name, Title (e.g. Project Manager)
	First name Last name, Title (e.g. Principal Lecturer)

The text section of the abstract is written to fit the space used on the page. The text section uses the “Body Text No Spacing” style.
Keywords:	keyword, keyword
___________________________________________________________

The originality of this thesis has been checked using Turnitin Originality Check service.
 
 
Contents
List of Abbreviations
1	Introduction	1
2	Chapter Heading	1
2.1	Subheading	1
2.2	Subheading	3
3	Document Structure	3
3.1	Tables	3
3.1.1	How to Create Tables in Word	4
3.1.2	Secondary Subheading	5
3.2	Quotes	5
3.3	Lists	5
3.4	Listings	6
3.5	Formulas	6
4	Alternative Text	7
4.1	How to Add Alternative Text to Figures	7
4.2	How to Add Alternative Text to Tables	8
5	Document Accessibility	8
5.1	Finish the Document Properties	8
5.2	Check the Accessibility of Your Thesis	9
5.3	Save Word Document as Accessible PDF	10
References	12
Appendices
Appendix 1: Appendix name
Appendix 2: Appendix name
 
List of Abbreviations
DBMS:	Database management system. Software for maintaining, querying and updating data and metadata in a database.
ORM:	Object-relational mapping. The set of rules for mapping objects in a programming language to records in a relational database, and vice versa.

 
Introduction
Write the introduction of your thesis here. Use line spacing 1.5 throughout the paper. Only the left edge is aligned, and the text is not hyphenated. Leave one blank line between paragraphs (press Enter once).
Begin a new paragraph at the left margin, that is, do not indent the first line.
Chapter Heading
The auto-generated table of contents uses heading styles. The table of contents is updated by selecting the whole text (Ctrl-A) and hitting F9.
Subheading
There must always be text or a new subheading below each heading. Do not place a figure or table below a heading with no text in between. Label each figure and table appropriately. Provide a number, caption and reference (if needed) below each figure (figure 1). Remember to mention each figure in text, telling the reader what they are supposed to see in it.
 
Figure 1. A conceptual model of the Company database.
An auto-numbered figure caption is inserted by right clicking the figure and selecting Insert caption. Type the caption in the opening dialogue window. Figure 2 shows how to enter the caption.
 
Figure 2. Entering the figure caption.
If the names of the built-in styles appear in a language other than English, you can change the default language of the Office package. To do this, select Office and Graphics / Office 2016 Language preferences from the operating system’s Windows menu, and choose English as the editing language.
Subheading
If subheadings are used, there should be at least two of them.
Document Structure
Tables
There must always be text or a new subheading below each heading. Do not place a figure or table below a heading with no text in between.
Table 1 shows an example of a table created with Word. Use “Table content” style to achieve the tighter spacing used in the tables. Also, place a caption above each table.
Table 1. Mean execution times of the selected sorting algorithms in the two scenarios.
Algorithm	Mean execution time (scenario 1)	Mean execution time (scenario 1)
Bubble sort	1,420 ms	13,700 ms
Quicksort	175 ms	548 ms
Insertion sort	1,080 ms	9,300 ms

Figure 3 displays how to create a caption above the table. The dialogue window appears by clicking on the square-shaped table selector near the top left corner of the table and selecting “Insert caption”.
 
Figure 3. Entering the data for table caption.
When a table caption has been created, change its style to Table caption.
How to Create Tables in Word
Create tables using Word's "Add a Table" feature. Do not use an image of a table, as screen readers cannot interpret the image. Make a header row and ensure the contents of the table cells are readable and in a logical order.
Once you have created a table, mark the top row of the table as the header row as follows:
	Place the mouse cursor on the top row of the table. This displays the Table Tools on the Ribbon.
	In Table Tools, click "Layout", and then click "Repeat Header Rows" (figure 4).
 
Figure 4. Marking the header row.
A properly marked header row improves the accessibility of the document.
Secondary Subheading
There must always be text or a new subheading below each heading.
Quotes
Quotes use the “Quote” style. The paragraph containing the citation passage (immediately before the citation) uses the “Body Text Before a Quote or List” style to leave a shorter paragraph spacing between the citation and the passage.
Direct quoting uses the “Quote” style of the template. A citation is given in the quotation.
After indentation, the text continues from the left edge in the “Body text” style.
Lists
A list in the text uses the “List” style. The paragraph before a list uses the “Body text before a quote or list” style.
When the list items are not sentences, they begin with a lowercase letter, and the last list item ends in a period. The thesis consists of
words
clauses
sentences
paragraphs
chapters.
When the list items are sentences, they begin with a capitalized letter, and the list items end in a period:
This is the first item in the list.
The second item of the list here contains a long text that spans multiple lines. The left edge aligns automatically.
This is the third item in the list.
The fourth item in the list is here.
Listings
A listing displays source code of a computer program (listing 1). Use “Code line” style to mark code lines, and create indentations with the Tab key. The caption should follow the “Listing caption” style.
def inventory():
	cur = db.cursor()
	sql = "SELECT Description FROM OBJECT WHERE Location='PLAYER'"
	cur.execute(sql)
	if cur.rowcount>=1:
		print("You carry the following items:")
		for row in cur.fetchall() :
			print (" - " + row[0])
	else:
		print("You don't carry anything.")
	return
A Python subroutine that outputs information about objects in possession of a player.
Formulas
You can insert numbered formulas that are displayed on separate rows:
	x=(-b±√(b^2-4ac))/2a	(1)
Insert a new formula by selecting Insert/Quick parts/Formula.
Alternative Text
According to accessibility requirements, figures must have alternative text. Alternative text is not the same thing as a caption. Alternative text is a description of the content of a figure read aloud by screen readers used by the visually impaired. It is not advisable to repeat the caption in the alternative text because screen readers read both contents.
When writing alternative text, think about what information you will not receive if you do not see the figure. Use short sentences and plain language. Tell the essential about the figure - you do not have to explain everything.
How to Add Alternative Text to Figures
An alternative text is given to a figure in a Word document as follows:
	Move the cursor over the figure and right-click.
	Select “Format Picture…” (figure 5).
	In the “Format Picture” window, select the third icon “Layout and Properties”.
	Select “Alt Text” and enter a description of the figure content in “Description”. Do not write anything under “Title”.
 
Figure 5. Adding alternative text to a figure.
There must always be text between a figure or table and a new figure or table or a new heading.
How to Add Alternative Text to Tables
Just like figures, tables need alternative text. To add that, first right-click the table selector near the top left corner of the table. Then, select “Table properties” and go to the “Alt text” tab. Type the alternative text into the “Description” field.
Document Accessibility
Finish the Document Properties
Once the content of your thesis is in order, finalise the document by specifying its properties. It is essential to ensure that the PDF file is accessible when you convert a Word file to PDF format. Type a title for the document in the “File” menu, under Info (figure 6). Enter the title of your thesis as the title.
 
Figure 6. Entering the title for the thesis.
Check the Accessibility of Your Thesis
Word has a feature that lets you check the accessibility of a document.
	On the “File” menu, click “Info” (figure 7).
	Then click “Check for Issues”.
	Click ”Check Accessibility”.
 
Figure 7. Opening the window for checking accessibility.
The “Accessibility Checker” pane will then appear on the right side of the Word. The results of the scan show possible errors and warnings. For more information about results, click the item name in the results list. Word also tells you the reason for the error, as well as gives repair instructions. At least fix any errors.
Save Word Document as Accessible PDF
Once you have checked your thesis for accessibility, convert it into an accessible PDF document.
	Create a PDF file using either the “Export” function (Create PDF) or the “Save As” function.
	In the save options, select “Document properties” and “Document structure” tags for accessibility.
	Click “Create bookmarks using Headings” (figure 8).
 
Figure 8. Creating the bookmarks using headings.
Do not use the “Print to PDF” function because the result is not an accessible PDF. 
References
Use one of the referencing systems below. Remove the one that you do not use.
Harvard (author-date) system:
The reference list entries need to be in alphabetical order according to the last name of the author mentioned first in the list of authors.
Davies, Barbara; Jameson, Peter & Smith, John. 2013. Advanced economics. Oxford: Oxford University Press.
Mitchell, John Arnold & Thomson, Magdalena. 2017. A guide to citation. London: London Publishings.

Vancouver (numbering) system:
Mitchell, John Arnold & Thomson, Magdalena. 2017. A guide to citation. London: London Publishings.
Davies, Barbara; Jameson, Peter & Smith, John. 2013. Advanced economics. Oxford: Oxford University Press.

 
Title of the Appendix
The appendices are not inserted into the table of contents automatically. Instead, they must be mentioned separately just below the auto-generated part of the table of contents.
Should you insert figures or tables into an appendix, Word numbers them automatically as if they were in the thesis main section. Fix the numbering of figures and tables in the appendixes manually so that the numbering starts from one in each appendix.
Below are instructions for adding and removing attachments so that the headers remain correct.
Instructions for adding a new attachment:
	Move the cursor to the end of the last existing attachment page.
	Choose the “Page Layout” tab. From the ribbon select “Page Break” / “Next Page” under “Section Breaks”. This completes the printing of the new attachment, but the number in its header is not correct.
	Double tap the header of the new attachment page with the wrong attachment number. If the “Link to previous” option is selected in the ribbon, press that button so that the option is no longer selected.
	Please correct the attachment number.
Instructions for removing an unnecessary attachment:
	First select the entire attached page and press “Delete” to delete its contents.
	When you are at the beginning of the attachment page you have emptied (see figure), double tap the header of the blank attachment page and press the “Link to Previous” button on the ribbon. The dialogue box appears (figure 1). Answer “Yes”.
 
Figure 1. Confirmation of deleting a header.
	From the “Home” tab, toggle hidden characters if they are not visible: 
	Remove the section break before the unnecessary attachment (figure 2).
 
Figure 2. Removal of a section break.
. 
Title of the Appendix
Content of the appendix is placed here
