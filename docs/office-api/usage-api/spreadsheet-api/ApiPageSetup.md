# ApiPageSetup

Class representing the page setup (print layout) of a worksheet.

## Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| AlignMarginsHeaderFooter | boolean | Returns or sets whether the header and footer margins are aligned with the page margins. |
| BottomMargin | number | Returns or sets the bottom margin size measured in millimeters. |
| CenterFooter | string | Returns or sets the center part of the (odd) footer. |
| CenterHeader | string | Returns or sets the center part of the (odd) header. |
| CenterHorizontally | boolean | Returns or sets whether the worksheet is centered horizontally on the page when printed. |
| CenterVertically | boolean | Returns or sets whether the worksheet is centered vertically on the page when printed. |
| DifferentFirstPageHeaderFooter | boolean | Returns or sets whether a different header and footer is used on the first printed page. |
| EvenPage | [ApiPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPage.md) | Returns the header and footer of the even pages. |
| FirstPage | [ApiPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPage.md) | Returns the header and footer of the first page. |
| FirstPageNumber | number \| null | Returns or sets the first page number (null means automatic). |
| FitToPagesTall | number | Returns or sets the number of pages tall the worksheet is scaled to when printed (0 means automatic). |
| FitToPagesWide | number | Returns or sets the number of pages wide the worksheet is scaled to when printed (0 means automatic). |
| FooterMargin | number | Returns or sets the distance from the bottom of the page to the footer, in millimeters. |
| HeaderMargin | number | Returns or sets the distance from the top of the page to the header, in millimeters. |
| LeftFooter | string | Returns or sets the left part of the (odd) footer. |
| LeftHeader | string | Returns or sets the left part of the (odd) header. |
| LeftMargin | number | Returns or sets the left margin size measured in millimeters. |
| OddAndEvenPagesHeaderFooter | boolean | Returns or sets whether different headers and footers are used on odd and even printed pages. |
| Orientation | [PageOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/PageOrientation.md) | Returns or sets the page orientation. |
| PaperSize | [PaperSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/PaperSize.md) | Returns or sets the paper size. |
| Parent | [ApiWorksheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet.md) | Returns the parent worksheet of the page setup. |
| PrintArea | string | Returns or sets the range to be printed (empty string prints the whole sheet). |
| PrintGridlines | boolean | Returns or sets whether the cell gridlines are printed. |
| PrintHeadings | boolean | Returns or sets whether the row and column headings are printed. |
| PrintTitleColumns | string | Returns or sets the columns repeated at the left of each printed page. |
| PrintTitleRows | string | Returns or sets the rows repeated at the top of each printed page. |
| RightFooter | string | Returns or sets the right part of the (odd) footer. |
| RightHeader | string | Returns or sets the right part of the (odd) header. |
| RightMargin | number | Returns or sets the right margin size measured in millimeters. |
| ScaleWithDocHeaderFooter | boolean | Returns or sets whether the header and footer are scaled with the document when printing. |
| TopMargin | number | Returns or sets the top margin size measured in millimeters. |
| Zoom | number | Returns or sets the print scaling factor in percent (10-400). |

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [GetAlignMarginsHeaderFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetAlignMarginsHeaderFooter.md) | boolean | Returns whether the header and footer margins are aligned with the page margins. |
| [GetBottomMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetBottomMargin.md) | number | Returns the size of the bottom margin. |
| [GetCenterFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetCenterFooter.md) | string | Returns the center part of the footer used when the worksheet is printed. |
| [GetCenterHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetCenterHeader.md) | string | Returns the center part of the header used when the worksheet is printed. |
| [GetCenterHorizontally](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetCenterHorizontally.md) | boolean | Returns whether the worksheet is centered horizontally on the page when printed. |
| [GetCenterVertically](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetCenterVertically.md) | boolean | Returns whether the worksheet is centered vertically on the page when printed. |
| [GetDifferentFirstPageHeaderFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetDifferentFirstPageHeaderFooter.md) | boolean | Returns whether a different header and footer is used on the first printed page. |
| [GetEvenPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetEvenPage.md) | [ApiPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPage.md) | Returns the header and footer of the even pages of the worksheet. The returned object is meaningful when [ApiPageSetup#GetOddAndEvenPagesHeaderFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetOddAndEvenPagesHeaderFooter.md) is enabled. |
| [GetFirstPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetFirstPage.md) | [ApiPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPage.md) | Returns the header and footer of the first page of the worksheet. The returned object is meaningful when [ApiPageSetup#GetDifferentFirstPageHeaderFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetDifferentFirstPageHeaderFooter.md) is enabled. |
| [GetFirstPageNumber](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetFirstPageNumber.md) | number \| null | Returns the first page number used when the worksheet is printed. Returns null when the page numbering is automatic. |
| [GetFitToPagesTall](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetFitToPagesTall.md) | number | Returns the number of pages tall the worksheet is scaled to when printed (0 means automatic). |
| [GetFitToPagesWide](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetFitToPagesWide.md) | number | Returns the number of pages wide the worksheet is scaled to when printed (0 means automatic). |
| [GetFooterMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetFooterMargin.md) | number | Returns the distance from the bottom of the page to the footer. |
| [GetHeaderMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetHeaderMargin.md) | number | Returns the distance from the top of the page to the header. |
| [GetLeftFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetLeftFooter.md) | string | Returns the left part of the footer used when the worksheet is printed. |
| [GetLeftHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetLeftHeader.md) | string | Returns the left part of the header used when the worksheet is printed. |
| [GetLeftMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetLeftMargin.md) | number | Returns the size of the left margin. |
| [GetOddAndEvenPagesHeaderFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetOddAndEvenPagesHeaderFooter.md) | boolean | Returns whether different headers and footers are used on odd and even printed pages. |
| [GetOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetOrientation.md) | [PageOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/PageOrientation.md) | Returns the page orientation used when the worksheet is printed. |
| [GetPaperSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetPaperSize.md) | [PaperSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/PaperSize.md) | Returns the paper size used when the worksheet is printed. |
| [GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetParent.md) | [ApiWorksheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet.md) | Returns the worksheet that owns this page setup. |
| [GetPrintArea](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetPrintArea.md) | string | Returns the range to be printed (the print area) as a string, or an empty string when the whole sheet is printed. |
| [GetPrintGridlines](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetPrintGridlines.md) | boolean | Returns whether cell gridlines are printed with the worksheet. |
| [GetPrintHeadings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetPrintHeadings.md) | boolean | Returns whether row and column headings are printed with the worksheet. |
| [GetPrintTitleColumns](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetPrintTitleColumns.md) | string | Returns the columns that are repeated at the left of each printed page, or an empty string if none. |
| [GetPrintTitleRows](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetPrintTitleRows.md) | string | Returns the rows that are repeated at the top of each printed page, or an empty string if none. |
| [GetRightFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetRightFooter.md) | string | Returns the right part of the footer used when the worksheet is printed. |
| [GetRightHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetRightHeader.md) | string | Returns the right part of the header used when the worksheet is printed. |
| [GetRightMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetRightMargin.md) | number | Returns the size of the right margin. |
| [GetScaleWithDocHeaderFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetScaleWithDocHeaderFooter.md) | boolean | Returns whether the header and footer are scaled with the document when it is scaled for printing. |
| [GetTopMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetTopMargin.md) | number | Returns the size of the top margin. |
| [GetZoom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetZoom.md) | number | Returns the scaling factor (in percent) used when the worksheet is printed. |
| [SetAlignMarginsHeaderFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetAlignMarginsHeaderFooter.md) | boolean | Sets whether the header and footer margins are aligned with the page margins. |
| [SetBottomMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetBottomMargin.md) | boolean | Sets the size of the bottom margin. |
| [SetCenterFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetCenterFooter.md) | boolean | Sets the center part of the footer used when the worksheet is printed. |
| [SetCenterHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetCenterHeader.md) | boolean | Sets the center part of the header used when the worksheet is printed. |
| [SetCenterHorizontally](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetCenterHorizontally.md) | boolean | Sets whether the worksheet is centered horizontally on the page when printed. |
| [SetCenterVertically](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetCenterVertically.md) | boolean | Sets whether the worksheet is centered vertically on the page when printed. |
| [SetDifferentFirstPageHeaderFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetDifferentFirstPageHeaderFooter.md) | boolean | Sets whether a different header and footer is used on the first printed page. |
| [SetFirstPageNumber](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetFirstPageNumber.md) | boolean | Sets the first page number used when the worksheet is printed. |
| [SetFitToPagesTall](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetFitToPagesTall.md) | boolean | Sets the number of pages tall the worksheet is scaled to when printed (0 means automatic). Setting this property turns on the "fit to page" mode. |
| [SetFitToPagesWide](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetFitToPagesWide.md) | boolean | Sets the number of pages wide the worksheet is scaled to when printed (0 means automatic). Setting this property turns on the "fit to page" mode. |
| [SetFooterMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetFooterMargin.md) | boolean | Sets the distance from the bottom of the page to the footer. |
| [SetHeaderMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetHeaderMargin.md) | boolean | Sets the distance from the top of the page to the header. |
| [SetLeftFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetLeftFooter.md) | boolean | Sets the left part of the footer used when the worksheet is printed. |
| [SetLeftHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetLeftHeader.md) | boolean | Sets the left part of the header used when the worksheet is printed. |
| [SetLeftMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetLeftMargin.md) | boolean | Sets the size of the left margin. |
| [SetOddAndEvenPagesHeaderFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetOddAndEvenPagesHeaderFooter.md) | boolean | Sets whether different headers and footers are used on odd and even printed pages. |
| [SetOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetOrientation.md) | boolean | Sets the page orientation used when the worksheet is printed. |
| [SetPaperSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetPaperSize.md) | boolean | Sets the paper size used when the worksheet is printed. |
| [SetPrintArea](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetPrintArea.md) | boolean | Sets the range to be printed (the print area). Pass an empty string to clear it and print the whole sheet. |
| [SetPrintGridlines](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetPrintGridlines.md) | boolean | Sets whether cell gridlines are printed with the worksheet. |
| [SetPrintHeadings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetPrintHeadings.md) | boolean | Sets whether row and column headings are printed with the worksheet. |
| [SetPrintTitleColumns](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetPrintTitleColumns.md) | boolean | Sets the columns that are repeated at the left of each printed page. Pass an empty string to clear them. |
| [SetPrintTitleRows](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetPrintTitleRows.md) | boolean | Sets the rows that are repeated at the top of each printed page. Pass an empty string to clear them. |
| [SetRightFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetRightFooter.md) | boolean | Sets the right part of the footer used when the worksheet is printed. |
| [SetRightHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetRightHeader.md) | boolean | Sets the right part of the header used when the worksheet is printed. |
| [SetRightMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetRightMargin.md) | boolean | Sets the size of the right margin. |
| [SetScaleWithDocHeaderFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetScaleWithDocHeaderFooter.md) | boolean | Sets whether the header and footer are scaled with the document when it is scaled for printing. |
| [SetTopMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetTopMargin.md) | boolean | Sets the size of the top margin. |
| [SetZoom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetZoom.md) | boolean | Sets the scaling factor (in percent) used when the worksheet is printed. Setting this property turns off the "fit to page" mode. |
