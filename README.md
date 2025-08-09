Advanced PDF Report Generator for GanitAnk
This repository contains a powerful, browser-based tool for automatically generating personalized PDF reports from Excel data. Developed for GanitAnk, this tool provides a high-speed, professional solution for creating custom college lists for students, complete with profile summaries and branded templates.

✨ Features
Bulk PDF Generation: Process multiple Excel files and student entries simultaneously to generate individual PDF reports.
Drag & Drop Interface: Easily upload your Excel data files, a base PDF template, and a concluding PDF page.
High-Speed Processing: Utilizes Web Workers to process PDF generation tasks in parallel, preventing UI freezing and ensuring a smooth experience even with large datasets.
Customizable Column Mapping: Advanced options allow you to specify which columns in your Excel file correspond to student profile data, college codes, names, and branches.
Dynamic Filename Templates: Define a template for output filenames using placeholders from the student's profile (e.g., {Name} {Percentile}).
Configuration Management: Save your column mappings and filename settings to a JSON file and load them later for consistent report generation.
Download All as ZIP: After generation, download all the created PDF files in a single, organized ZIP archive.
Real-time Progress Tracking: Monitor the PDF creation process with a live progress bar and a detailed log of operations.
Error Handling: The tool provides clear error messages for issues like missing student names or file parsing problems, helping you quickly identify and fix data issues.
No Server Required: The entire process runs in the user's browser, ensuring data privacy and eliminating the need for a backend server.

🚀 How to Use
Open the PDF MAKER -V2.html file in your web browser.

Step 1 : Upload Files:
Excel Data File(s): Drag and drop one or more Excel files (.xlsx, .xls, .csv) containing the student data.

Step 2 : Base Template PDF: Upload a single-page PDF that will be used as the template for every page of the generated college list.

Step 3 : Last Page(s) PDF: Upload a PDF file containing the final pages that will be appended to every generated report.

(Optional) Configure Advanced Options:
Expand the "Advanced Options" section.
Enter the Excel column letters for profile labels/values, college codes, names, and branches.
Set a custom filename template using placeholders like {Name}.
You can Save your current settings or Load a previously saved configuration file.
Generate PDFs: Once all required files are uploaded, the "Generate PDFs" button will be enabled. Click it to start the process.

Step 4 : Download:
As PDFs are generated, they will appear in the results area, where you can download them individually.
Once all tasks are complete, click the "Download All as ZIP" button to get a ZIP file containing all the reports, neatly organized into folders based on the source Excel file.


⚙️ Input File Structure (Excel)
The tool expects the Excel data to be structured in blocks. Each block represents one student's report.
Student Profile: The first 8 rows of a block should contain the student's profile information.
Column A (or as specified in settings): Profile field label (e.g., "Name", "Percentile").
Column B (or as specified in settings): Profile field value.
College List: Starting from row 10 of a block.
Column A (or as specified in settings): College Code.
Column B (or as specified in settings): College Name.
Column C (or as specified in settings): Branch Name.
The tool identifies a new student block whenever it encounters a row where the profile label column contains the text "Name".


🛠️ Technologies Used
HTML5/CSS3: For the main structure and styling.
Tailwind CSS: For a utility-first CSS workflow.
JavaScript (ES6+): For all the client-side logic.
SheetJS (xlsx.js): For parsing Excel files in the browser.
pdf-lib: For creating and modifying PDF documents.
JSZip: For creating ZIP archives.
FileSaver.js: For saving files on the client-side.

📄 License
This project is licensed under the MIT License. See the LICENSE file for details.
