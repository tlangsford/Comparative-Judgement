# Comparative-Judgement
This HTML app converts a teacher’s pairwise comparisons into z-scores for clear, intuitive assessment of student work. 

##### Key Features
- Compare student scripts side by side in full, scrollable PDFs.
- Flag and add comments to scripts for review, plagiarism, and more.
- Download results with scripts, rankings, and z-scores in one click.
- Full keyboard shortcut support (press `S` to toggle shortcut view)
- Runs fully offline in any modern web browser. 
##### How to Use 
- I recommend you open the HTML file in DuckDuckGo, which is fastest. Safari and Firefox come second in terms of speed. 
- If you’re using Chrome, you’ll only be able to Copy the Results unless chrome://settings/content/automaticDownloads has “Sites can ask to automatically download multiple files” ticked. 
##### References
- Inspired by: https://www.nomoremarking.com/
- The advantages of rankit: https://digitalcommons.wayne.edu/coe_tbf/5/
- Chained comparisons reduce cognitive load: https://doi.org/10.1007/s10798-011-9189-x 
##### FAQ: No .docx/.doc support? 
This functionality is “missing” because there is no way to present Microsoft files within an offline HTML document. Here are some work-arounds: 
1. You can **enforce PDF submission** in all online assignment submission tools, forcing students to export their own work as a PDF and saving you time. 
2. Alternatively, you can **batch-convert** .docx files to PDFs offline. 
	- Download **LibreOffice**. 
	- Use this terminal script: `soffice --headless --convert-to pdf --outdir /Users/xyz/Desktop/output '/Users/xyz/Documents/Longer Path Name/input/'*.docx`
3. You can similarly batch-convert **images** to PDFs offline. 
	- Download **XnConvert** and specify “PDF” as your desired output format. 
### Version History
###### 0.0.1–6
Python scripts with PDF-to-Image conversion.
###### 0.1.0
Overhauled matching system.
Reduced excessive pair generation.
Shortened total comparison time.
###### 0.1.1
Added Undo button between option buttons.
Bound ‘U’ and ‘u’ to undo action.
Disabled undo when no undo possible.
Added “Ranking Complete!” message with comparison count and close button.
Inserted loading bar near percentage complete.
###### 0.2.0–6
Removed PDF.JS; embedded PDFs using `<iframe>`.
Fixed scroll and visuals by switching to HTML.
Enabled independent scroll on hover for each script.
“Ranking Complete!” and “Start New Ranking” buttons.
Replaced PDF titles with “Script 1” and “Script 2”.
Changed header to “Comparative Judgement”.
Enabled folder selection for scripts.
Randomised presentation order.
Added percent progress to window title.
###### 0.3.0
Added “Download Results” button.
Added a CSV export with Rank, Name, Flag, Comment columns.
###### 0.4.0 (Fri 13 Jun)
Enforced chained comparison logic with presentation rules:
1. The initial presentation of scripts is randomised.
2. In each new comparison, one script stays on the same side of the page;
3. No script appears more than twice in a row;
4. If neither rule 1 or 2 can be satisfied, the result is random.
Inserted “Flag This Script” buttons with `F` and `G` shortcuts.
Dialog included checkboxes and comment field.
Appended flag and comment to CSV.
Preserved anonymity during ranking.
Rewrote codebase for full compliance.
###### 0.4.1 (Fri 13 Jun)
Mapped `A` to Left is Better; `D` to Right is Better.
Used ⚐ for unflagged scripts, ⚑ for flagged or commented.
Bound `Escape` to “Save Flag” and removed “Cancel” from flag dialog.
Displayed Escape below button.
Prepared explanation for switching to Tim-sort or similar.
###### 0.4.2 (Fri 13 Jun)
All code now with help from Gemini Pro.
Results are now automatically downloaded on completion.
Added Escape / Return shortcuts for “New Ranking” / “Download”.
Added favicon.
###### 0.4.3 (Sun 15 Jun)
“Choose PDF Files” shortcut added (`Enter`).
Added folder uploads.
Cursor is now already in flag text box.
###### 0.4.4 (Mon 16 Jun)
Backtick now shows/hides shortcuts.
###### 0.5.0 (Thu 19 Jun)
Comparative Sorting Logic now uses MergeSort.
This reduces marking load from $\frac{x(x - 1)}{2}$ to $\frac{n}{\log_2(n)}$.
For example, ranking 100 items now takes ~664 comparisons, not 4,950. 
Tweaked progress counts.
###### 0.5.1 (Sun 22 Jun)
Progress bar now anchored to top when shortcuts are hidden.
Initial order of script presentation is randomised.
Added one-click copy of CSV results (with `Enter` shortcut).
###### 1.0.0 (Sun 22 Jun) — **Major Release** 
Added rankit-based auto-calculated z-scores to the CSV.
###### 1.0.1 (Thu 26 Jun)
Flag Script dialogue now replaces non-flagged script.
This allows the user to read scripts while flagging.
Added colour schemes which cycle with `C`.
Fixed slightly pixel-imperfect buttons.
###### 1.0.2–5 (Mon 30 Jun) 
Now accepts .txt and .html files. 
Now accepts common `<image>` .png, .jpg, .jpeg, .gif, .svg files. 
Now accepts common `<audio>` and `<video>` files. 
Keyboard shortcuts are now toggled with `K`.
###### 1.1.0 (Mon 30 Jun)
Added a corrected Z-Score column which standardises Rankit-Z estimate.
###### 1.2.0–2 (Mon 20 Jun)
Names and ranks are now displayed in a table at the end of the judging process. 
Added text arrows ← → to the flag dialogue boxes. 
Flag buttons now change to a dark colour when scripts are flagged. 
Bug fix: `C` and `K` are now properly ignored while commenting; `Escape` is not. 
###### 1.3.0
Changed the first screen to look more like the Marking Criteria app. 
