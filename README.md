# Automated College List PDF Generator

![Project Screenshot](https://raw.githubusercontent.com/vj4614/automated-college-list-pdf-maker/main/screenshot.png)

A powerful, browser-based tool designed for **GanitAnk** to automate the creation of personalized college list PDF reports directly from Excel data. This tool is built for efficiency, processing hundreds of student reports in minutes without needing a server.

---

## ✨ Features

* **Bulk PDF Generation**: Process multiple Excel files and student entries simultaneously to generate individual, multi-page PDF reports.
* **Drag & Drop Simplicity**: An intuitive interface to upload your Excel data, a base PDF template for report pages, and a concluding PDF for the final pages.
* **High-Speed Parallel Processing**: Leverages Web Workers to run PDF generation tasks in the background, preventing the UI from freezing and ensuring a smooth experience with large datasets.
* **Dynamic Filename Templates**: Define a custom filename format using placeholders from the student's profile (e.g., `{Name} {Percentile}`).
* **Advanced Column Mapping**: Precisely map the columns in your Excel files to the data fields required for the reports (e.g., Profile Labels, College Codes, Branch Names).
* **Configuration Management**: Save your column mappings and filename settings to a `config.json` file and load them in future sessions for consistent, repeatable results.
* **Complete Privacy**: The entire process runs in the user's browser. No data is ever uploaded to a server.
* **Download All as ZIP**: Once generation is complete, download all the created PDFs in a single, organized ZIP archive, with files sorted into folders based on their source Excel file.

---

## 🚀 How to Use

1.  **Open the `PDF MAKER -V2.html` file in your web browser.**
2.  **Upload Your Files**:
    * **Excel Data File(s)**: Drag and drop one or more `.xlsx` files containing the student data.
    * **Base Template PDF**: Upload the single-page PDF to be used as the background for the college list pages.
    * **Last Page(s) PDF**: Upload a PDF containing the final pages that will be appended to every report.
3.  **(Optional) Configure Advanced Options**:
    * Expand the **Advanced Options** section to map your Excel columns and set a filename template.
    * You can **Save** your current settings or **Load** a previously saved configuration file.
4.  **Generate PDFs**: Once all files are uploaded, click the **Generate PDFs** button.
5.  **Download**: Download reports individually as they are created, or wait for the process to finish and click **Download All as ZIP**.

---

## ⚙️ Configuration & Input File Requirements

For the tool to work correctly, your Excel files must follow a specific structure.

### 1. Excel File Structure

The tool processes data in blocks, where each block represents one student's report.

* **Student Profile Block**: The first 8 rows of a block must contain the student's profile information.
    * The first column (e.g., `A`) should have the profile field label (e.g., "Name", "Percentile").
    * The second column (e.g., `B`) should have the corresponding value.
* **College List Block**: This section starts from row 10 and contains the list of colleges for that student. The columns must match the mappings you define in the advanced options.
* **Student Separator**: A new student block begins whenever the tool finds the text `Name` in the profile label column.

### 2. Advanced Options

The "Advanced Options" section allows you to customize how the tool reads your Excel files.

| Option                | Description                                                                                             | Default Value     |
| --------------------- | ------------------------------------------------------------------------------------------------------- | ----------------- |
| `Profile Label Col`   | The column for student profile labels (like "Name", "Rank").                                            | `A`               |
| `Profile Value Col`   | The column for the student's profile values.                                                            | `B`               |
| `College Code Col`    | The column containing the unique college code.                                                          | `A`               |
| `College Name Col`    | The column for the full college name.                                                                   | `B`               |
| `Branch Name Col`     | The column containing the engineering branch or stream.                                                 | `C`               |
| `Filename Template`   | The output format for PDF filenames. Use placeholders like `{Name}` that match your profile labels. | `{Name} {Percentile}` |

### 3. Saving & Loading Configuration

Use the **Save Config** button to download a `config.json` file of your current settings. Use the **Load Config** button to upload this file in a later session to instantly apply your settings.

**Example `config.json` file:**

```json
{
  "profileLabelCol": "A",
  "profileValueCol": "B",
  "collegeCodeCol": "A",
  "collegeNameCol": "B",
  "branchCol": "C",
  "filenameTemplate": "{Name} {Percentile}"
}
