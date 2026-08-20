heya!

**MetaExtractor** is a comprehensive tool designed to extract hidden metadata from various file types (Images, Videos, Audio, PDFs, and Office documents), score the associated privacy risks, flag signs of tampering, and automatically sanitize files to protect user privacy. 

It is a Universal Metadata Extraction tool which supports various file types such as `.jpg`, `.png`,`.pdf`,`.mov`,`.mp4`,`.wav`,`m4a`,`.docx`,`.xlsx` and `.pptx`.

It also has a privacy Risk scoring engine, through which it automatically assigns risk categories(Low,Medium,High) to extracted metadata fields.

**Phase1** 
`MetadataCore` the core metadata extraction engine 
- building an engine that can handle any type of file and can give "field name → value" pairs.

  It has 3 classes.
  - ImageMetadataextractor : handles .jpg/.png using the MetadataExtractor NuGet package
  - PdfMetadataextractor :handles .pdf using PdfSharp or iText7
  - OfficeMetadataExtractor : handles .docx/.xlsx/.pptx (these are secretly ZIP files containing XML — you unzip them and read core.xml/app.xml)


directory structure

IMetadataExtractor
 ├── ImageMetadataExtractor   (.jpg, .png, .mp4, .mov)  <- MetadataExtractor lib covers both
 ├── AudioMetadataExtractor   (.mp3, .wav, .m4a)          <- TagLib#
 ├── PdfMetadataExtractor     (.pdf)
 └── OfficeMetadataExtractor  (.docx, .xlsx, .pptx)


 

