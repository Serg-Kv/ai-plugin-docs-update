# Changelog

The list of changes for Office JavaScript API.

## Version 10.0

### Breaking changes

- Renamed the `ApiChart/SetAxieNumFormat` method to `ApiChart/SetAxisNumFormat` in [Document API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetAxisNumFormat.md), [Spreadsheet API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetAxisNumFormat.md), [Presentation API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetAxisNumFormat.md), and [PDF API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetAxisNumFormat.md). The old name still works as an alias.
- Removed the `ApiTextWidget` class from PDF API, which had no effect. Text field widgets are [ApiBaseWidget](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget.md) objects. For more information, see [PDF API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api.md).
- Removed the `ApiRun/SetPosition` method from Spreadsheet API, Presentation API, and PDF API. The method had no effect in these editors.
- Removed the `ApiRun/SetHighlight` method from Spreadsheet API.
- Replaced the `Shd` type with the [ApiShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShd.md) class in Document API. The `GetShd` methods (for example, [ApiParagraph/GetShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/GetShd.md)) now return an `ApiShd` object, and [Api/CreateShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateShd.md) creates one.
- Replaced the Spreadsheet API `ApiColor` class with the common [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColor.md) class shared with the other editors. [ApiColor/GetRGB](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColor/Methods/GetRGB.md) now returns an `{r, g, b}` object instead of a `0xRRGGBB` number. Methods that return a color no longer convert theme colors to RGB, so [ApiColor/IsThemeColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColor/Methods/IsThemeColor.md) and [ApiColor/GetThemeName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColor/Methods/GetThemeName.md) work on the returned color.

### Changed methods

- Updated the [ApiDocument/Search](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/Search.md), [ApiParagraph/Search](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/Search.md), [ApiTable/Search](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/Search.md), [ApiTableRow/Search](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableRow/Methods/Search.md), [ApiTableCell/Search](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableCell/Methods/Search.md), and [ApiBlockLvlSdt/Search](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/Search.md) methods in Document API - added regular expression (`RegExp` in `sText`) support. When a `RegExp` is passed, `isMatchCase` is ignored; use the `i` flag instead.
- Updated the [ApiRange/Find](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/Find.md) and [ApiRange/Replace](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/Replace.md) methods in Spreadsheet API - added wildcard (`Wildcards`) and regular expression (`RegExp` in `What`) support.
- Updated the [Api/Intersect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/Intersect.md) method in Spreadsheet API - it now accepts from 2 to 30 ranges.
- Updated the [ApiRange/SetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/SetValue.md) method in Spreadsheet API - it now returns `false` if the value was not set; a formula set to a multi-cell range now shifts relative references from the top-left cell.
- Updated the [ApiRange/GetFormula](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/GetFormula.md) method in Spreadsheet API - it now returns an array of formulas for a multi-cell range.
- Updated the [ApiParagraph/SetStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/SetStyle.md), [ApiParaPr/SetStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/SetStyle.md), [ApiRun/SetStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun/Methods/SetStyle.md), and [ApiTextPr/SetStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/SetStyle.md) methods in Document API - they now accept a style name, and `null` removes the style.
- Updated the [ApiParagraph/SetNumbering](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/SetNumbering.md) and [ApiParaPr/SetNumPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/SetNumPr.md) methods in Document API - `null` now removes numbering.

### Document methods

#### Api methods

- Added the [Api/CreateMath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateMath.md) method to Document API.
- Added the [Api/CreateShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateShadow.md) method to Document API.
- Added the [Api/CreateShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateShd.md) method to Document API.
- Added the [Api/MergeShapes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/MergeShapes.md) method to Document API.

#### ApiBlockLvlSdt methods

- Added the [ApiBlockLvlSdt/GetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/GetColor.md) method to Document API.
- Added the [ApiBlockLvlSdt/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/GetParent.md) method to Document API.
- Added the [ApiBlockLvlSdt/SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/SetColor.md) method to Document API.

#### ApiChart methods

- Added the [ApiChart/GetAllowOverlap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/GetAllowOverlap.md) method to Document API.
- Added the [ApiChart/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/GetDescription.md) method to Document API.
- Added the [ApiChart/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/GetFill.md) method to Document API.
- Added the [ApiChart/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/GetLine.md) method to Document API.
- Added the [ApiChart/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/GetLockAspect.md) method to Document API.
- Added the [ApiChart/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/GetShadow.md) method to Document API.
- Added the [ApiChart/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/GetTextRange.md) method to Document API.
- Added the [ApiChart/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/GetType.md) method to Document API.
- Added the [ApiChart/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/HasTextContent.md) method to Document API.
- Added the [ApiChart/SetAllowOverlap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetAllowOverlap.md) method to Document API.
- Added the [ApiChart/SetDataLabelsTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetDataLabelsTextPr.md) method to Document API.
- Added the [ApiChart/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetDescription.md) method to Document API.
- Added the [ApiChart/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetFill.md) method to Document API.
- Added the [ApiChart/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetLine.md) method to Document API.
- Added the [ApiChart/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetLockAspect.md) method to Document API.
- Added the [ApiChart/SetPointDataLabelTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetPointDataLabelTextPr.md) method to Document API.
- Added the [ApiChart/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetShadow.md) method to Document API.
- Added the [ApiChart/SetShowDataTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetShowDataTable.md) method to Document API.

#### ApiChartSeries methods

- Added the [ApiChartSeries/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChartSeries/Methods/GetType.md) method to Document API.

#### ApiCheckBoxForm methods

- Added the [ApiCheckBoxForm/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/GetParent.md) method to Document API.
- Added the [ApiCheckBoxForm/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/GetPosInParent.md) method to Document API.

#### ApiColor methods

- Added the [ApiColor/GetTintAndShade](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor/Methods/GetTintAndShade.md) method to Document API.

#### ApiComboBoxForm methods

- Added the [ApiComboBoxForm/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/GetParent.md) method to Document API.
- Added the [ApiComboBoxForm/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/GetPosInParent.md) method to Document API.

#### ApiComplexForm methods

- Added the [ApiComplexForm/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetParent.md) method to Document API.
- Added the [ApiComplexForm/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetPosInParent.md) method to Document API.

#### ApiDateForm methods

- Added the [ApiDateForm/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/GetParent.md) method to Document API.
- Added the [ApiDateForm/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/GetPosInParent.md) method to Document API.

#### ApiDocument methods

- Added the [ApiDocument/GetActiveTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetActiveTable.md) method to Document API.
- Added the [ApiDocument/GetElementIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetElementIndex.md) method to Document API.
- Added the [ApiDocument/GetTablesOfContents](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetTablesOfContents.md) method to Document API.
- Added the [ApiDocument/GetTablesOfFigures](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetTablesOfFigures.md) method to Document API.
- Added the [ApiDocument/MoveCursorToFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/MoveCursorToFooter.md) method to Document API.
- Added the [ApiDocument/MoveCursorToHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/MoveCursorToHeader.md) method to Document API.
- Added the [ApiDocument/MoveCursorToMainDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/MoveCursorToMainDocument.md) method to Document API.
- Added the [ApiDocument/MoveToNextCell](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/MoveToNextCell.md) method to Document API.
- Added the [ApiDocument/MoveToPrevCell](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/MoveToPrevCell.md) method to Document API.
- Added the [ApiDocument/SelectCurrentSentence](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/SelectCurrentSentence.md) method to Document API.

#### ApiDocumentContent methods

- Added the [ApiDocumentContent/GetElementIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/GetElementIndex.md) method to Document API.

#### ApiDocumentVisitor class

- Added the [ApiDocumentVisitor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentVisitor.md) class to Document API.
- Added the [ApiDocumentVisitor/Stop](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentVisitor/Methods/Stop.md) method to Document API.

#### ApiDrawing methods

- Added the [ApiDrawing/GetAllowOverlap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/GetAllowOverlap.md) method to Document API.
- Added the [ApiDrawing/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/GetDescription.md) method to Document API.
- Added the [ApiDrawing/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/GetFill.md) method to Document API.
- Added the [ApiDrawing/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/GetLine.md) method to Document API.
- Added the [ApiDrawing/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/GetLockAspect.md) method to Document API.
- Added the [ApiDrawing/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/GetShadow.md) method to Document API.
- Added the [ApiDrawing/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/GetTextRange.md) method to Document API.
- Added the [ApiDrawing/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/GetTitle.md) method to Document API.
- Added the [ApiDrawing/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/HasTextContent.md) method to Document API.
- Added the [ApiDrawing/SetAllowOverlap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/SetAllowOverlap.md) method to Document API.
- Added the [ApiDrawing/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/SetDescription.md) method to Document API.
- Added the [ApiDrawing/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/SetFill.md) method to Document API.
- Added the [ApiDrawing/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/SetLine.md) method to Document API.
- Added the [ApiDrawing/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/SetLockAspect.md) method to Document API.
- Added the [ApiDrawing/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/SetShadow.md) method to Document API.
- Added the [ApiDrawing/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/SetTitle.md) method to Document API.

#### ApiDropCap class

- Added the [ApiDropCap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap.md) class to Document API.
- Added the [ApiDropCap/Clear](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/Clear.md) method to Document API.
- Added the [ApiDropCap/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/GetClassType.md) method to Document API.
- Added the [ApiDropCap/GetDistanceFromText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/GetDistanceFromText.md) method to Document API.
- Added the [ApiDropCap/GetLinesToDrop](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/GetLinesToDrop.md) method to Document API.
- Added the [ApiDropCap/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/GetParent.md) method to Document API.
- Added the [ApiDropCap/GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/GetPosition.md) method to Document API.
- Added the [ApiDropCap/SetDistanceFromText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/SetDistanceFromText.md) method to Document API.
- Added the [ApiDropCap/SetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/SetFontFamily.md) method to Document API.
- Added the [ApiDropCap/SetLinesToDrop](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/SetLinesToDrop.md) method to Document API.
- Added the [ApiDropCap/SetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDropCap/Methods/SetPosition.md) method to Document API.

#### ApiFill methods

- Added the [ApiFill/GetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFill/Methods/GetColor.md) method to Document API.
- Added the [ApiFill/GetTransparent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFill/Methods/GetTransparent.md) method to Document API.
- Added the [ApiFill/SetTransparent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFill/Methods/SetTransparent.md) method to Document API.

#### ApiFormBase methods

- Added the [ApiFormBase/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetParent.md) method to Document API.
- Added the [ApiFormBase/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetPosInParent.md) method to Document API.

#### ApiGeometry methods

- Added the [ApiGeometry/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGeometry/Methods/GetClassType.md) method to Document API.

#### ApiGroup methods

- Added the [ApiGroup/GetAllowOverlap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGroup/Methods/GetAllowOverlap.md) method to Document API.
- Added the [ApiGroup/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGroup/Methods/GetDescription.md) method to Document API.
- Added the [ApiGroup/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGroup/Methods/GetFill.md) method to Document API.
- Added the [ApiGroup/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGroup/Methods/GetLine.md) method to Document API.
- Added the [ApiGroup/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGroup/Methods/GetLockAspect.md) method to Document API.
- Added the [ApiGroup/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGroup/Methods/GetShadow.md) method to Document API.
- Added the [ApiGroup/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGroup/Methods/GetTextRange.md) method to Document API.
- Added the [ApiGroup/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGroup/Methods/GetTitle.md) method to Document API.
- Added the [ApiGroup/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGroup/Methods/HasTextContent.md) method to Document API.
- Added the [ApiGroup/SetAllowOverlap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGroup/Methods/SetAllowOverlap.md) method to Document API.
- Added the [ApiGroup/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGroup/Methods/SetDescription.md) method to Document API.
- Added the [ApiGroup/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGroup/Methods/SetFill.md) method to Document API.
- Added the [ApiGroup/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGroup/Methods/SetLine.md) method to Document API.
- Added the [ApiGroup/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGroup/Methods/SetLockAspect.md) method to Document API.
- Added the [ApiGroup/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGroup/Methods/SetShadow.md) method to Document API.
- Added the [ApiGroup/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGroup/Methods/SetTitle.md) method to Document API.

#### ApiHyperlink methods

- Added the [ApiHyperlink/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiHyperlink/Methods/GetParent.md) method to Document API.
- Added the [ApiHyperlink/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiHyperlink/Methods/GetPosInParent.md) method to Document API.

#### ApiImage methods

- Added the [ApiImage/GetAllowOverlap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiImage/Methods/GetAllowOverlap.md) method to Document API.
- Added the [ApiImage/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiImage/Methods/GetDescription.md) method to Document API.
- Added the [ApiImage/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiImage/Methods/GetFill.md) method to Document API.
- Added the [ApiImage/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiImage/Methods/GetLine.md) method to Document API.
- Added the [ApiImage/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiImage/Methods/GetLockAspect.md) method to Document API.
- Added the [ApiImage/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiImage/Methods/GetShadow.md) method to Document API.
- Added the [ApiImage/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiImage/Methods/GetTextRange.md) method to Document API.
- Added the [ApiImage/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiImage/Methods/GetTitle.md) method to Document API.
- Added the [ApiImage/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiImage/Methods/HasTextContent.md) method to Document API.
- Added the [ApiImage/SetAllowOverlap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiImage/Methods/SetAllowOverlap.md) method to Document API.
- Added the [ApiImage/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiImage/Methods/SetDescription.md) method to Document API.
- Added the [ApiImage/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiImage/Methods/SetFill.md) method to Document API.
- Added the [ApiImage/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiImage/Methods/SetLine.md) method to Document API.
- Added the [ApiImage/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiImage/Methods/SetLockAspect.md) method to Document API.
- Added the [ApiImage/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiImage/Methods/SetShadow.md) method to Document API.
- Added the [ApiImage/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiImage/Methods/SetTitle.md) method to Document API.

#### ApiInlineLvlSdt methods

- Added the [ApiInlineLvlSdt/GetElementIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/GetElementIndex.md) method to Document API.
- Added the [ApiInlineLvlSdt/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/GetParent.md) method to Document API.
- Added the [ApiInlineLvlSdt/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/GetPosInParent.md) method to Document API.

#### ApiMath class

- Added the [ApiMath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiMath.md) class to Document API.
- Added the [ApiMath/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiMath/Methods/GetClassType.md) method to Document API.
- Added the [ApiMath/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiMath/Methods/GetParent.md) method to Document API.
- Added the [ApiMath/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiMath/Methods/GetPosInParent.md) method to Document API.
- Added the [ApiMath/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiMath/Methods/GetText.md) method to Document API.

#### ApiOleObject methods

- Added the [ApiOleObject/GetAllowOverlap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/GetAllowOverlap.md) method to Document API.
- Added the [ApiOleObject/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/GetDescription.md) method to Document API.
- Added the [ApiOleObject/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/GetFill.md) method to Document API.
- Added the [ApiOleObject/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/GetLine.md) method to Document API.
- Added the [ApiOleObject/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/GetLockAspect.md) method to Document API.
- Added the [ApiOleObject/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/GetShadow.md) method to Document API.
- Added the [ApiOleObject/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/GetTextRange.md) method to Document API.
- Added the [ApiOleObject/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/GetTitle.md) method to Document API.
- Added the [ApiOleObject/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/HasTextContent.md) method to Document API.
- Added the [ApiOleObject/SetAllowOverlap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/SetAllowOverlap.md) method to Document API.
- Added the [ApiOleObject/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/SetDescription.md) method to Document API.
- Added the [ApiOleObject/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/SetFill.md) method to Document API.
- Added the [ApiOleObject/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/SetLine.md) method to Document API.
- Added the [ApiOleObject/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/SetLockAspect.md) method to Document API.
- Added the [ApiOleObject/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/SetShadow.md) method to Document API.
- Added the [ApiOleObject/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/SetTitle.md) method to Document API.

#### ApiParagraph methods

- Added the [ApiParagraph/GetDropCap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/GetDropCap.md) method to Document API.
- Added the [ApiParagraph/GetElementIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/GetElementIndex.md) method to Document API.
- Added the [ApiParagraph/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/GetParent.md) method to Document API.
- Added the [ApiParagraph/IsEmpty](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/IsEmpty.md) method to Document API.
- Added the [ApiParagraph/SetDropCap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/SetDropCap.md) method to Document API.
- Added the [ApiParagraph/SetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/SetLanguage.md) method to Document API.

#### ApiPictureForm methods

- Added the [ApiPictureForm/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/GetParent.md) method to Document API.
- Added the [ApiPictureForm/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/GetPosInParent.md) method to Document API.

#### ApiRange methods

- Added the [ApiRange/SetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/SetLanguage.md) method to Document API.

#### ApiRun methods

- Added the [ApiRun/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun/Methods/GetParent.md) method to Document API.
- Added the [ApiRun/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun/Methods/GetPosInParent.md) method to Document API.
- Added the [ApiRun/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun/Methods/SetText.md) method to Document API.

#### ApiShadow class

- Added the [ApiShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShadow.md) class to Document API.
- Added the [ApiShadow/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShadow/Methods/GetClassType.md) method to Document API.
- Added the [ApiShadow/GetSettings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShadow/Methods/GetSettings.md) method to Document API.

#### ApiShape methods

- Added the [ApiShape/GetAllowOverlap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape/Methods/GetAllowOverlap.md) method to Document API.
- Added the [ApiShape/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape/Methods/GetDescription.md) method to Document API.
- Added the [ApiShape/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape/Methods/GetLockAspect.md) method to Document API.
- Added the [ApiShape/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape/Methods/GetShadow.md) method to Document API.
- Added the [ApiShape/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape/Methods/GetTextRange.md) method to Document API.
- Added the [ApiShape/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape/Methods/GetTitle.md) method to Document API.
- Added the [ApiShape/GetVerticalTextAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape/Methods/GetVerticalTextAlign.md) method to Document API.
- Added the [ApiShape/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape/Methods/HasTextContent.md) method to Document API.
- Added the [ApiShape/SetAllowOverlap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape/Methods/SetAllowOverlap.md) method to Document API.
- Added the [ApiShape/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape/Methods/SetDescription.md) method to Document API.
- Added the [ApiShape/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape/Methods/SetLockAspect.md) method to Document API.
- Added the [ApiShape/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape/Methods/SetShadow.md) method to Document API.
- Added the [ApiShape/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape/Methods/SetTitle.md) method to Document API.

#### ApiShd class

- Added the [ApiShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShd.md) class to Document API.
- Added the [ApiShd/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShd/Methods/GetClassType.md) method to Document API.
- Added the [ApiShd/GetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShd/Methods/GetColor.md) method to Document API.
- Added the [ApiShd/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShd/Methods/GetType.md) method to Document API.

#### ApiSignatureForm methods

- Added the [ApiSignatureForm/GetImage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetImage.md) method to Document API.
- Added the [ApiSignatureForm/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetParent.md) method to Document API.
- Added the [ApiSignatureForm/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetPosInParent.md) method to Document API.
- Added the [ApiSignatureForm/SetImage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/SetImage.md) method to Document API.

#### ApiSmartArt methods

- Added the [ApiSmartArt/GetAllowOverlap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSmartArt/Methods/GetAllowOverlap.md) method to Document API.
- Added the [ApiSmartArt/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSmartArt/Methods/GetDescription.md) method to Document API.
- Added the [ApiSmartArt/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSmartArt/Methods/GetFill.md) method to Document API.
- Added the [ApiSmartArt/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSmartArt/Methods/GetLine.md) method to Document API.
- Added the [ApiSmartArt/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSmartArt/Methods/GetLockAspect.md) method to Document API.
- Added the [ApiSmartArt/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSmartArt/Methods/GetShadow.md) method to Document API.
- Added the [ApiSmartArt/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSmartArt/Methods/GetTextRange.md) method to Document API.
- Added the [ApiSmartArt/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSmartArt/Methods/GetTitle.md) method to Document API.
- Added the [ApiSmartArt/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSmartArt/Methods/HasTextContent.md) method to Document API.
- Added the [ApiSmartArt/SetAllowOverlap](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSmartArt/Methods/SetAllowOverlap.md) method to Document API.
- Added the [ApiSmartArt/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSmartArt/Methods/SetDescription.md) method to Document API.
- Added the [ApiSmartArt/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSmartArt/Methods/SetFill.md) method to Document API.
- Added the [ApiSmartArt/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSmartArt/Methods/SetLine.md) method to Document API.
- Added the [ApiSmartArt/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSmartArt/Methods/SetLockAspect.md) method to Document API.
- Added the [ApiSmartArt/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSmartArt/Methods/SetShadow.md) method to Document API.
- Added the [ApiSmartArt/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSmartArt/Methods/SetTitle.md) method to Document API.

#### ApiStroke methods

- Added the [ApiStroke/GetBeginArrow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiStroke/Methods/GetBeginArrow.md) method to Document API.
- Added the [ApiStroke/GetCapType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiStroke/Methods/GetCapType.md) method to Document API.
- Added the [ApiStroke/GetEndArrow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiStroke/Methods/GetEndArrow.md) method to Document API.
- Added the [ApiStroke/GetJoinType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiStroke/Methods/GetJoinType.md) method to Document API.
- Added the [ApiStroke/SetBeginArrow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiStroke/Methods/SetBeginArrow.md) method to Document API.
- Added the [ApiStroke/SetCapType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiStroke/Methods/SetCapType.md) method to Document API.
- Added the [ApiStroke/SetEndArrow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiStroke/Methods/SetEndArrow.md) method to Document API.
- Added the [ApiStroke/SetJoinType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiStroke/Methods/SetJoinType.md) method to Document API.

#### ApiTable methods

- Added the [ApiTable/GetColumnWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/GetColumnWidth.md) method to Document API.
- Added the [ApiTable/GetColumnsCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/GetColumnsCount.md) method to Document API.
- Added the [ApiTable/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/GetParent.md) method to Document API.
- Added the [ApiTable/GetSelectedCells](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/GetSelectedCells.md) method to Document API.
- Added the [ApiTable/GetSelectedColumnsCells](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/GetSelectedColumnsCells.md) method to Document API.
- Added the [ApiTable/GetSelectedRows](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/GetSelectedRows.md) method to Document API.
- Added the [ApiTable/GetTableLook](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/GetTableLook.md) method to Document API.
- Added the [ApiTable/SelectRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/SelectRange.md) method to Document API.
- Added the [ApiTable/SetColumnWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/SetColumnWidth.md) method to Document API.
- Added the [ApiTable/SetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/SetHeight.md) method to Document API.

#### ApiTableOfContents class

- Added the [ApiTableOfContents](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfContents.md) class to Document API.
- Added the [ApiTableOfContents/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfContents/Methods/Delete.md) method to Document API.
- Added the [ApiTableOfContents/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfContents/Methods/GetClassType.md) method to Document API.
- Added the [ApiTableOfContents/GetIncludePageNumbers](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfContents/Methods/GetIncludePageNumbers.md) method to Document API.
- Added the [ApiTableOfContents/GetLowerHeadingLevel](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfContents/Methods/GetLowerHeadingLevel.md) method to Document API.
- Added the [ApiTableOfContents/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfContents/Methods/GetParent.md) method to Document API.
- Added the [ApiTableOfContents/GetRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfContents/Methods/GetRange.md) method to Document API.
- Added the [ApiTableOfContents/GetRightAlignPageNumbers](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfContents/Methods/GetRightAlignPageNumbers.md) method to Document API.
- Added the [ApiTableOfContents/GetUpperHeadingLevel](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfContents/Methods/GetUpperHeadingLevel.md) method to Document API.
- Added the [ApiTableOfContents/GetUseHyperlinks](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfContents/Methods/GetUseHyperlinks.md) method to Document API.
- Added the [ApiTableOfContents/SetIncludePageNumbers](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfContents/Methods/SetIncludePageNumbers.md) method to Document API.
- Added the [ApiTableOfContents/SetLowerHeadingLevel](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfContents/Methods/SetLowerHeadingLevel.md) method to Document API.
- Added the [ApiTableOfContents/SetPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfContents/Methods/SetPr.md) method to Document API.
- Added the [ApiTableOfContents/SetRightAlignPageNumbers](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfContents/Methods/SetRightAlignPageNumbers.md) method to Document API.
- Added the [ApiTableOfContents/SetUpperHeadingLevel](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfContents/Methods/SetUpperHeadingLevel.md) method to Document API.
- Added the [ApiTableOfContents/SetUseHyperlinks](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfContents/Methods/SetUseHyperlinks.md) method to Document API.
- Added the [ApiTableOfContents/Update](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfContents/Methods/Update.md) method to Document API.

#### ApiTableOfFigures class

- Added the [ApiTableOfFigures](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfFigures.md) class to Document API.
- Added the [ApiTableOfFigures/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfFigures/Methods/Delete.md) method to Document API.
- Added the [ApiTableOfFigures/GetCaption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfFigures/Methods/GetCaption.md) method to Document API.
- Added the [ApiTableOfFigures/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfFigures/Methods/GetClassType.md) method to Document API.
- Added the [ApiTableOfFigures/GetIncludeLabel](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfFigures/Methods/GetIncludeLabel.md) method to Document API.
- Added the [ApiTableOfFigures/GetIncludePageNumbers](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfFigures/Methods/GetIncludePageNumbers.md) method to Document API.
- Added the [ApiTableOfFigures/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfFigures/Methods/GetParent.md) method to Document API.
- Added the [ApiTableOfFigures/GetRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfFigures/Methods/GetRange.md) method to Document API.
- Added the [ApiTableOfFigures/GetRightAlignPageNumbers](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfFigures/Methods/GetRightAlignPageNumbers.md) method to Document API.
- Added the [ApiTableOfFigures/GetUseHyperlinks](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfFigures/Methods/GetUseHyperlinks.md) method to Document API.
- Added the [ApiTableOfFigures/SetCaption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfFigures/Methods/SetCaption.md) method to Document API.
- Added the [ApiTableOfFigures/SetIncludeLabel](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfFigures/Methods/SetIncludeLabel.md) method to Document API.
- Added the [ApiTableOfFigures/SetIncludePageNumbers](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfFigures/Methods/SetIncludePageNumbers.md) method to Document API.
- Added the [ApiTableOfFigures/SetPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfFigures/Methods/SetPr.md) method to Document API.
- Added the [ApiTableOfFigures/SetRightAlignPageNumbers](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfFigures/Methods/SetRightAlignPageNumbers.md) method to Document API.
- Added the [ApiTableOfFigures/SetUseHyperlinks](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfFigures/Methods/SetUseHyperlinks.md) method to Document API.
- Added the [ApiTableOfFigures/Update](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableOfFigures/Methods/Update.md) method to Document API.

#### ApiTableRow methods

- Added the [ApiTableRow/GetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableRow/Methods/GetHeight.md) method to Document API.
- Added the [ApiTableRow/SetRowPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableRow/Methods/SetRowPr.md) method to Document API.

#### ApiTablesOfContents class

- Added the [ApiTablesOfContents](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTablesOfContents.md) class to Document API.
- Added the [ApiTablesOfContents/Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTablesOfContents/Methods/Add.md) method to Document API.
- Added the [ApiTablesOfContents/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTablesOfContents/Methods/GetClassType.md) method to Document API.
- Added the [ApiTablesOfContents/GetCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTablesOfContents/Methods/GetCount.md) method to Document API.
- Added the [ApiTablesOfContents/GetItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTablesOfContents/Methods/GetItem.md) method to Document API.
- Added the [ApiTablesOfContents/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTablesOfContents/Methods/GetParent.md) method to Document API.

#### ApiTablesOfFigures class

- Added the [ApiTablesOfFigures](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTablesOfFigures.md) class to Document API.
- Added the [ApiTablesOfFigures/Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTablesOfFigures/Methods/Add.md) method to Document API.
- Added the [ApiTablesOfFigures/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTablesOfFigures/Methods/GetClassType.md) method to Document API.
- Added the [ApiTablesOfFigures/GetCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTablesOfFigures/Methods/GetCount.md) method to Document API.
- Added the [ApiTablesOfFigures/GetItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTablesOfFigures/Methods/GetItem.md) method to Document API.
- Added the [ApiTablesOfFigures/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTablesOfFigures/Methods/GetParent.md) method to Document API.

#### ApiTextForm methods

- Added the [ApiTextForm/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetParent.md) method to Document API.
- Added the [ApiTextForm/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetPosInParent.md) method to Document API.

#### Document types

- Added the [ChartTypeLegacy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ChartTypeLegacy.md) type to the simple type definitions.
- Added the [ComparisonPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ComparisonPr.md) type to the simple type definitions.
- Added the [LineCapType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/LineCapType.md) type to the simple type definitions.
- Added the [LineEndSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/LineEndSize.md) type to the simple type definitions.
- Added the [LineEndType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/LineEndType.md) type to the simple type definitions.
- Added the [LineJoinType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/LineJoinType.md) type to the simple type definitions.
- Added the [ParagraphLikeContainer](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ParagraphLikeContainer.md) type to the simple type definitions.
- Added the [ShadowSettings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ShadowSettings.md) type to the simple type definitions.
- Added the [ShapesMergeOperation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ShapesMergeOperation.md) type to the simple type definitions.
- Added the [TableLook](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/TableLook.md) type to the simple type definitions.

### Form methods

#### ApiCheckBoxForm methods

- Added the [ApiCheckBoxForm/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiCheckBoxForm/Methods/GetParent.md) method to Form API.
- Added the [ApiCheckBoxForm/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiCheckBoxForm/Methods/GetPosInParent.md) method to Form API.

#### ApiComboBoxForm methods

- Added the [ApiComboBoxForm/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiComboBoxForm/Methods/GetParent.md) method to Form API.
- Added the [ApiComboBoxForm/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiComboBoxForm/Methods/GetPosInParent.md) method to Form API.

#### ApiComplexForm methods

- Added the [ApiComplexForm/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiComplexForm/Methods/GetParent.md) method to Form API.
- Added the [ApiComplexForm/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiComplexForm/Methods/GetPosInParent.md) method to Form API.

#### ApiDateForm methods

- Added the [ApiDateForm/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDateForm/Methods/GetParent.md) method to Form API.
- Added the [ApiDateForm/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDateForm/Methods/GetPosInParent.md) method to Form API.

#### ApiFormBase methods

- Added the [ApiFormBase/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormBase/Methods/GetParent.md) method to Form API.
- Added the [ApiFormBase/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormBase/Methods/GetPosInParent.md) method to Form API.

#### ApiPictureForm methods

- Added the [ApiPictureForm/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiPictureForm/Methods/GetParent.md) method to Form API.
- Added the [ApiPictureForm/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiPictureForm/Methods/GetPosInParent.md) method to Form API.

#### ApiSignatureForm methods

- Added the [ApiSignatureForm/GetImage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiSignatureForm/Methods/GetImage.md) method to Form API.
- Added the [ApiSignatureForm/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiSignatureForm/Methods/GetParent.md) method to Form API.
- Added the [ApiSignatureForm/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiSignatureForm/Methods/GetPosInParent.md) method to Form API.
- Added the [ApiSignatureForm/SetImage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiSignatureForm/Methods/SetImage.md) method to Form API.

#### ApiTextForm methods

- Added the [ApiTextForm/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiTextForm/Methods/GetParent.md) method to Form API.
- Added the [ApiTextForm/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiTextForm/Methods/GetPosInParent.md) method to Form API.

#### Form types

- Added the [ParagraphLikeContainer](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/ParagraphLikeContainer.md) type to the simple type definitions.

### Spreadsheet methods

#### Api methods

- Added the [Api/Calculate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/Calculate.md) method to Spreadsheet API.
- Added the [Api/CreateMath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/CreateMath.md) method to Spreadsheet API.
- Added the [Api/CreateShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/CreateShadow.md) method to Spreadsheet API.
- Added the [Api/CreateShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/CreateShd.md) method to Spreadsheet API.
- Added the [Api/GetByInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/GetByInternalId.md) method to Spreadsheet API.
- Added the [Api/MergeShapes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/MergeShapes.md) method to Spreadsheet API.
- Added the [Api/Redraw](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/Redraw.md) method to Spreadsheet API.

#### ApiAboveAverage methods

- Added the [ApiAboveAverage/GetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/GetStopIfTrue.md) method to Spreadsheet API.
- Added the [ApiAboveAverage/SetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/SetStopIfTrue.md) method to Spreadsheet API.

#### ApiBullet methods

- Added the [ApiBullet/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiBullet/Methods/ToJSON.md) method to Spreadsheet API.

#### ApiChart methods

- Added the [ApiChart/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/GetDescription.md) method to Spreadsheet API.
- Added the [ApiChart/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/GetFill.md) method to Spreadsheet API.
- Added the [ApiChart/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/GetInternalId.md) method to Spreadsheet API.
- Added the [ApiChart/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/GetLine.md) method to Spreadsheet API.
- Added the [ApiChart/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/GetLockAspect.md) method to Spreadsheet API.
- Added the [ApiChart/GetPosX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/GetPosX.md) method to Spreadsheet API.
- Added the [ApiChart/GetPosY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/GetPosY.md) method to Spreadsheet API.
- Added the [ApiChart/GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/GetPosition.md) method to Spreadsheet API.
- Added the [ApiChart/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/GetShadow.md) method to Spreadsheet API.
- Added the [ApiChart/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/GetTextRange.md) method to Spreadsheet API.
- Added the [ApiChart/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/GetType.md) method to Spreadsheet API.
- Added the [ApiChart/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/HasTextContent.md) method to Spreadsheet API.
- Added the [ApiChart/SetDataLabelsTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetDataLabelsTextPr.md) method to Spreadsheet API.
- Added the [ApiChart/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetDescription.md) method to Spreadsheet API.
- Added the [ApiChart/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetFill.md) method to Spreadsheet API.
- Added the [ApiChart/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetLine.md) method to Spreadsheet API.
- Added the [ApiChart/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetLockAspect.md) method to Spreadsheet API.
- Added the [ApiChart/SetPointDataLabelTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetPointDataLabelTextPr.md) method to Spreadsheet API.
- Added the [ApiChart/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetShadow.md) method to Spreadsheet API.
- Added the [ApiChart/SetShowDataTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetShowDataTable.md) method to Spreadsheet API.

#### ApiChartSeries methods

- Added the [ApiChartSeries/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChartSeries/Methods/GetType.md) method to Spreadsheet API.

#### ApiColor methods

- Added the [ApiColor/GetTintAndShade](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColor/Methods/GetTintAndShade.md) method to Spreadsheet API.

#### ApiColorScale methods

- Added the [ApiColorScale/GetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetStopIfTrue.md) method to Spreadsheet API.
- Added the [ApiColorScale/SetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/SetStopIfTrue.md) method to Spreadsheet API.

#### ApiDatabar methods

- Added the [ApiDatabar/GetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetStopIfTrue.md) method to Spreadsheet API.
- Added the [ApiDatabar/SetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetStopIfTrue.md) method to Spreadsheet API.

#### ApiDocumentContent methods

- Added the [ApiDocumentContent/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDocumentContent/Methods/GetTextRange.md) method to Spreadsheet API.

#### ApiDrawing methods

- Added the [ApiDrawing/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/GetDescription.md) method to Spreadsheet API.
- Added the [ApiDrawing/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/GetFill.md) method to Spreadsheet API.
- Added the [ApiDrawing/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/GetInternalId.md) method to Spreadsheet API.
- Added the [ApiDrawing/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/GetLine.md) method to Spreadsheet API.
- Added the [ApiDrawing/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/GetLockAspect.md) method to Spreadsheet API.
- Added the [ApiDrawing/GetPosX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/GetPosX.md) method to Spreadsheet API.
- Added the [ApiDrawing/GetPosY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/GetPosY.md) method to Spreadsheet API.
- Added the [ApiDrawing/GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/GetPosition.md) method to Spreadsheet API.
- Added the [ApiDrawing/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/GetShadow.md) method to Spreadsheet API.
- Added the [ApiDrawing/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/GetTextRange.md) method to Spreadsheet API.
- Added the [ApiDrawing/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/GetTitle.md) method to Spreadsheet API.
- Added the [ApiDrawing/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/HasTextContent.md) method to Spreadsheet API.
- Added the [ApiDrawing/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/SetDescription.md) method to Spreadsheet API.
- Added the [ApiDrawing/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/SetFill.md) method to Spreadsheet API.
- Added the [ApiDrawing/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/SetLine.md) method to Spreadsheet API.
- Added the [ApiDrawing/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/SetLockAspect.md) method to Spreadsheet API.
- Added the [ApiDrawing/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/SetShadow.md) method to Spreadsheet API.
- Added the [ApiDrawing/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/SetTitle.md) method to Spreadsheet API.

#### ApiFill methods

- Added the [ApiFill/GetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFill/Methods/GetColor.md) method to Spreadsheet API.
- Added the [ApiFill/GetTransparent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFill/Methods/GetTransparent.md) method to Spreadsheet API.
- Added the [ApiFill/SetTransparent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFill/Methods/SetTransparent.md) method to Spreadsheet API.

#### ApiFormatCondition methods

- Added the [ApiFormatCondition/GetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetStopIfTrue.md) method to Spreadsheet API.
- Added the [ApiFormatCondition/SetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetStopIfTrue.md) method to Spreadsheet API.

#### ApiGeometry methods

- Added the [ApiGeometry/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGeometry/Methods/GetClassType.md) method to Spreadsheet API.

#### ApiGroup methods

- Added the [ApiGroup/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetDescription.md) method to Spreadsheet API.
- Added the [ApiGroup/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetFill.md) method to Spreadsheet API.
- Added the [ApiGroup/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetInternalId.md) method to Spreadsheet API.
- Added the [ApiGroup/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetLine.md) method to Spreadsheet API.
- Added the [ApiGroup/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetLockAspect.md) method to Spreadsheet API.
- Added the [ApiGroup/GetPosX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetPosX.md) method to Spreadsheet API.
- Added the [ApiGroup/GetPosY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetPosY.md) method to Spreadsheet API.
- Added the [ApiGroup/GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetPosition.md) method to Spreadsheet API.
- Added the [ApiGroup/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetShadow.md) method to Spreadsheet API.
- Added the [ApiGroup/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetTextRange.md) method to Spreadsheet API.
- Added the [ApiGroup/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetTitle.md) method to Spreadsheet API.
- Added the [ApiGroup/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/HasTextContent.md) method to Spreadsheet API.
- Added the [ApiGroup/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetDescription.md) method to Spreadsheet API.
- Added the [ApiGroup/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetFill.md) method to Spreadsheet API.
- Added the [ApiGroup/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetLine.md) method to Spreadsheet API.
- Added the [ApiGroup/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetLockAspect.md) method to Spreadsheet API.
- Added the [ApiGroup/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetShadow.md) method to Spreadsheet API.
- Added the [ApiGroup/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetTitle.md) method to Spreadsheet API.
- Added the [ApiGroup/Ungroup](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/Ungroup.md) method to Spreadsheet API.

#### ApiHeaderFooter class

- Added the [ApiHeaderFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiHeaderFooter.md) class to Spreadsheet API.
- Added the [ApiHeaderFooter/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiHeaderFooter/Methods/GetText.md) method to Spreadsheet API.
- Added the [ApiHeaderFooter/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiHeaderFooter/Methods/SetText.md) method to Spreadsheet API.

#### ApiHyperlink methods

- Added the [ApiHyperlink/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiHyperlink/Methods/Delete.md) method to Spreadsheet API.
- Added the [ApiHyperlink/GetAddress](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiHyperlink/Methods/GetAddress.md) method to Spreadsheet API.
- Added the [ApiHyperlink/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiHyperlink/Methods/GetName.md) method to Spreadsheet API.
- Added the [ApiHyperlink/GetRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiHyperlink/Methods/GetRange.md) method to Spreadsheet API.
- Added the [ApiHyperlink/GetScreenTip](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiHyperlink/Methods/GetScreenTip.md) method to Spreadsheet API.
- Added the [ApiHyperlink/GetSubAddress](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiHyperlink/Methods/GetSubAddress.md) method to Spreadsheet API.
- Added the [ApiHyperlink/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiHyperlink/Methods/GetTextRange.md) method to Spreadsheet API.
- Added the [ApiHyperlink/GetTextToDisplay](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiHyperlink/Methods/GetTextToDisplay.md) method to Spreadsheet API.
- Added the [ApiHyperlink/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiHyperlink/Methods/GetType.md) method to Spreadsheet API.
- Added the [ApiHyperlink/SetAddress](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiHyperlink/Methods/SetAddress.md) method to Spreadsheet API.
- Added the [ApiHyperlink/SetScreenTip](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiHyperlink/Methods/SetScreenTip.md) method to Spreadsheet API.
- Added the [ApiHyperlink/SetSubAddress](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiHyperlink/Methods/SetSubAddress.md) method to Spreadsheet API.
- Added the [ApiHyperlink/SetTextToDisplay](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiHyperlink/Methods/SetTextToDisplay.md) method to Spreadsheet API.

#### ApiIconSetCondition methods

- Added the [ApiIconSetCondition/GetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/GetStopIfTrue.md) method to Spreadsheet API.
- Added the [ApiIconSetCondition/SetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/SetStopIfTrue.md) method to Spreadsheet API.

#### ApiImage methods

- Added the [ApiImage/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiImage/Methods/GetDescription.md) method to Spreadsheet API.
- Added the [ApiImage/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiImage/Methods/GetFill.md) method to Spreadsheet API.
- Added the [ApiImage/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiImage/Methods/GetInternalId.md) method to Spreadsheet API.
- Added the [ApiImage/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiImage/Methods/GetLine.md) method to Spreadsheet API.
- Added the [ApiImage/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiImage/Methods/GetLockAspect.md) method to Spreadsheet API.
- Added the [ApiImage/GetPosX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiImage/Methods/GetPosX.md) method to Spreadsheet API.
- Added the [ApiImage/GetPosY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiImage/Methods/GetPosY.md) method to Spreadsheet API.
- Added the [ApiImage/GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiImage/Methods/GetPosition.md) method to Spreadsheet API.
- Added the [ApiImage/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiImage/Methods/GetShadow.md) method to Spreadsheet API.
- Added the [ApiImage/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiImage/Methods/GetTextRange.md) method to Spreadsheet API.
- Added the [ApiImage/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiImage/Methods/GetTitle.md) method to Spreadsheet API.
- Added the [ApiImage/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiImage/Methods/HasTextContent.md) method to Spreadsheet API.
- Added the [ApiImage/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiImage/Methods/SetDescription.md) method to Spreadsheet API.
- Added the [ApiImage/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiImage/Methods/SetFill.md) method to Spreadsheet API.
- Added the [ApiImage/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiImage/Methods/SetLine.md) method to Spreadsheet API.
- Added the [ApiImage/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiImage/Methods/SetLockAspect.md) method to Spreadsheet API.
- Added the [ApiImage/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiImage/Methods/SetShadow.md) method to Spreadsheet API.
- Added the [ApiImage/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiImage/Methods/SetTitle.md) method to Spreadsheet API.

#### ApiMath class

- Added the [ApiMath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiMath.md) class to Spreadsheet API.
- Added the [ApiMath/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiMath/Methods/GetClassType.md) method to Spreadsheet API.
- Added the [ApiMath/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiMath/Methods/GetText.md) method to Spreadsheet API.

#### ApiOleObject methods

- Added the [ApiOleObject/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetDescription.md) method to Spreadsheet API.
- Added the [ApiOleObject/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetFill.md) method to Spreadsheet API.
- Added the [ApiOleObject/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetInternalId.md) method to Spreadsheet API.
- Added the [ApiOleObject/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetLine.md) method to Spreadsheet API.
- Added the [ApiOleObject/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetLockAspect.md) method to Spreadsheet API.
- Added the [ApiOleObject/GetPosX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetPosX.md) method to Spreadsheet API.
- Added the [ApiOleObject/GetPosY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetPosY.md) method to Spreadsheet API.
- Added the [ApiOleObject/GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetPosition.md) method to Spreadsheet API.
- Added the [ApiOleObject/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetShadow.md) method to Spreadsheet API.
- Added the [ApiOleObject/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetTextRange.md) method to Spreadsheet API.
- Added the [ApiOleObject/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetTitle.md) method to Spreadsheet API.
- Added the [ApiOleObject/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/HasTextContent.md) method to Spreadsheet API.
- Added the [ApiOleObject/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetDescription.md) method to Spreadsheet API.
- Added the [ApiOleObject/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetFill.md) method to Spreadsheet API.
- Added the [ApiOleObject/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetLine.md) method to Spreadsheet API.
- Added the [ApiOleObject/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetLockAspect.md) method to Spreadsheet API.
- Added the [ApiOleObject/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetShadow.md) method to Spreadsheet API.
- Added the [ApiOleObject/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetTitle.md) method to Spreadsheet API.

#### ApiPage class

- Added the [ApiPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPage.md) class to Spreadsheet API.
- Added the [ApiPage/GetCenterFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPage/Methods/GetCenterFooter.md) method to Spreadsheet API.
- Added the [ApiPage/GetCenterHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPage/Methods/GetCenterHeader.md) method to Spreadsheet API.
- Added the [ApiPage/GetLeftFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPage/Methods/GetLeftFooter.md) method to Spreadsheet API.
- Added the [ApiPage/GetLeftHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPage/Methods/GetLeftHeader.md) method to Spreadsheet API.
- Added the [ApiPage/GetRightFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPage/Methods/GetRightFooter.md) method to Spreadsheet API.
- Added the [ApiPage/GetRightHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPage/Methods/GetRightHeader.md) method to Spreadsheet API.

#### ApiPageSetup class

- Added the [ApiPageSetup](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup.md) class to Spreadsheet API.
- Added the [ApiPageSetup/GetAlignMarginsHeaderFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetAlignMarginsHeaderFooter.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetBottomMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetBottomMargin.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetCenterFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetCenterFooter.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetCenterHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetCenterHeader.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetCenterHorizontally](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetCenterHorizontally.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetCenterVertically](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetCenterVertically.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetDifferentFirstPageHeaderFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetDifferentFirstPageHeaderFooter.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetEvenPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetEvenPage.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetFirstPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetFirstPage.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetFirstPageNumber](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetFirstPageNumber.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetFitToPagesTall](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetFitToPagesTall.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetFitToPagesWide](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetFitToPagesWide.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetFooterMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetFooterMargin.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetHeaderMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetHeaderMargin.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetLeftFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetLeftFooter.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetLeftHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetLeftHeader.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetLeftMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetLeftMargin.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetOddAndEvenPagesHeaderFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetOddAndEvenPagesHeaderFooter.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetOrientation.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetPaperSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetPaperSize.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetParent.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetPrintArea](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetPrintArea.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetPrintGridlines](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetPrintGridlines.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetPrintHeadings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetPrintHeadings.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetPrintTitleColumns](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetPrintTitleColumns.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetPrintTitleRows](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetPrintTitleRows.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetRightFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetRightFooter.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetRightHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetRightHeader.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetRightMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetRightMargin.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetScaleWithDocHeaderFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetScaleWithDocHeaderFooter.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetTopMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetTopMargin.md) method to Spreadsheet API.
- Added the [ApiPageSetup/GetZoom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/GetZoom.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetAlignMarginsHeaderFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetAlignMarginsHeaderFooter.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetBottomMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetBottomMargin.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetCenterFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetCenterFooter.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetCenterHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetCenterHeader.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetCenterHorizontally](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetCenterHorizontally.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetCenterVertically](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetCenterVertically.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetDifferentFirstPageHeaderFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetDifferentFirstPageHeaderFooter.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetFirstPageNumber](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetFirstPageNumber.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetFitToPagesTall](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetFitToPagesTall.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetFitToPagesWide](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetFitToPagesWide.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetFooterMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetFooterMargin.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetHeaderMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetHeaderMargin.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetLeftFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetLeftFooter.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetLeftHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetLeftHeader.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetLeftMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetLeftMargin.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetOddAndEvenPagesHeaderFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetOddAndEvenPagesHeaderFooter.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetOrientation.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetPaperSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetPaperSize.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetPrintArea](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetPrintArea.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetPrintGridlines](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetPrintGridlines.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetPrintHeadings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetPrintHeadings.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetPrintTitleColumns](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetPrintTitleColumns.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetPrintTitleRows](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetPrintTitleRows.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetRightFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetRightFooter.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetRightHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetRightHeader.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetRightMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetRightMargin.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetScaleWithDocHeaderFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetScaleWithDocHeaderFooter.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetTopMargin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetTopMargin.md) method to Spreadsheet API.
- Added the [ApiPageSetup/SetZoom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPageSetup/Methods/SetZoom.md) method to Spreadsheet API.

#### ApiParagraph methods

- Added the [ApiParagraph/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/GetTextRange.md) method to Spreadsheet API.
- Added the [ApiParagraph/IsEmpty](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/IsEmpty.md) method to Spreadsheet API.
- Added the [ApiParagraph/SetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/SetLanguage.md) method to Spreadsheet API.
- Added the [ApiParagraph/ToHtml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/ToHtml.md) method to Spreadsheet API.

#### ApiPivotDataField methods

- Added the [ApiPivotDataField/Group](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/Group.md) method to Spreadsheet API.

#### ApiPivotField methods

- Added the [ApiPivotField/Group](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/Group.md) method to Spreadsheet API.

#### ApiPivotTable methods

- Added the [ApiPivotTable/GetHasAutoFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetHasAutoFormat.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetHasAutoFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetHasAutoFormat.md) method to Spreadsheet API.

#### ApiRange methods

- Added the [ApiRange/GetHyperlinks](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/GetHyperlinks.md) method to Spreadsheet API.
- Added the [ApiRange/RemoveDuplicates](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/RemoveDuplicates.md) method to Spreadsheet API.

#### ApiRun methods

- Added the [ApiRun/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRun/Methods/GetTextRange.md) method to Spreadsheet API.
- Added the [ApiRun/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRun/Methods/SetText.md) method to Spreadsheet API.

#### ApiShadow class

- Added the [ApiShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShadow.md) class to Spreadsheet API.
- Added the [ApiShadow/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShadow/Methods/GetClassType.md) method to Spreadsheet API.
- Added the [ApiShadow/GetSettings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShadow/Methods/GetSettings.md) method to Spreadsheet API.

#### ApiShape methods

- Added the [ApiShape/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/GetDescription.md) method to Spreadsheet API.
- Added the [ApiShape/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/GetInternalId.md) method to Spreadsheet API.
- Added the [ApiShape/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/GetLockAspect.md) method to Spreadsheet API.
- Added the [ApiShape/GetPosX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/GetPosX.md) method to Spreadsheet API.
- Added the [ApiShape/GetPosY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/GetPosY.md) method to Spreadsheet API.
- Added the [ApiShape/GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/GetPosition.md) method to Spreadsheet API.
- Added the [ApiShape/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/GetShadow.md) method to Spreadsheet API.
- Added the [ApiShape/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/GetTextRange.md) method to Spreadsheet API.
- Added the [ApiShape/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/GetTitle.md) method to Spreadsheet API.
- Added the [ApiShape/GetVerticalTextAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/GetVerticalTextAlign.md) method to Spreadsheet API.
- Added the [ApiShape/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/HasTextContent.md) method to Spreadsheet API.
- Added the [ApiShape/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/SetDescription.md) method to Spreadsheet API.
- Added the [ApiShape/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/SetLockAspect.md) method to Spreadsheet API.
- Added the [ApiShape/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/SetShadow.md) method to Spreadsheet API.
- Added the [ApiShape/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/SetTitle.md) method to Spreadsheet API.

#### ApiShd class

- Added the [ApiShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShd.md) class to Spreadsheet API.
- Added the [ApiShd/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShd/Methods/GetClassType.md) method to Spreadsheet API.
- Added the [ApiShd/GetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShd/Methods/GetColor.md) method to Spreadsheet API.
- Added the [ApiShd/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShd/Methods/GetType.md) method to Spreadsheet API.

#### ApiSmartArt methods

- Added the [ApiSmartArt/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSmartArt/Methods/GetDescription.md) method to Spreadsheet API.
- Added the [ApiSmartArt/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSmartArt/Methods/GetFill.md) method to Spreadsheet API.
- Added the [ApiSmartArt/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSmartArt/Methods/GetInternalId.md) method to Spreadsheet API.
- Added the [ApiSmartArt/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSmartArt/Methods/GetLine.md) method to Spreadsheet API.
- Added the [ApiSmartArt/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSmartArt/Methods/GetLockAspect.md) method to Spreadsheet API.
- Added the [ApiSmartArt/GetPosX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSmartArt/Methods/GetPosX.md) method to Spreadsheet API.
- Added the [ApiSmartArt/GetPosY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSmartArt/Methods/GetPosY.md) method to Spreadsheet API.
- Added the [ApiSmartArt/GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSmartArt/Methods/GetPosition.md) method to Spreadsheet API.
- Added the [ApiSmartArt/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSmartArt/Methods/GetShadow.md) method to Spreadsheet API.
- Added the [ApiSmartArt/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSmartArt/Methods/GetTextRange.md) method to Spreadsheet API.
- Added the [ApiSmartArt/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSmartArt/Methods/GetTitle.md) method to Spreadsheet API.
- Added the [ApiSmartArt/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSmartArt/Methods/HasTextContent.md) method to Spreadsheet API.
- Added the [ApiSmartArt/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSmartArt/Methods/SetDescription.md) method to Spreadsheet API.
- Added the [ApiSmartArt/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSmartArt/Methods/SetFill.md) method to Spreadsheet API.
- Added the [ApiSmartArt/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSmartArt/Methods/SetLine.md) method to Spreadsheet API.
- Added the [ApiSmartArt/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSmartArt/Methods/SetLockAspect.md) method to Spreadsheet API.
- Added the [ApiSmartArt/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSmartArt/Methods/SetShadow.md) method to Spreadsheet API.
- Added the [ApiSmartArt/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSmartArt/Methods/SetTitle.md) method to Spreadsheet API.

#### ApiStroke methods

- Added the [ApiStroke/GetBeginArrow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiStroke/Methods/GetBeginArrow.md) method to Spreadsheet API.
- Added the [ApiStroke/GetCapType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiStroke/Methods/GetCapType.md) method to Spreadsheet API.
- Added the [ApiStroke/GetEndArrow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiStroke/Methods/GetEndArrow.md) method to Spreadsheet API.
- Added the [ApiStroke/GetJoinType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiStroke/Methods/GetJoinType.md) method to Spreadsheet API.
- Added the [ApiStroke/SetBeginArrow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiStroke/Methods/SetBeginArrow.md) method to Spreadsheet API.
- Added the [ApiStroke/SetCapType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiStroke/Methods/SetCapType.md) method to Spreadsheet API.
- Added the [ApiStroke/SetEndArrow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiStroke/Methods/SetEndArrow.md) method to Spreadsheet API.
- Added the [ApiStroke/SetJoinType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiStroke/Methods/SetJoinType.md) method to Spreadsheet API.

#### ApiTextPr methods

- Added the [ApiTextPr/SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextPr/Methods/SetColor.md) method to Spreadsheet API.
- Added the [ApiTextPr/SetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextPr/Methods/SetLanguage.md) method to Spreadsheet API.

#### ApiTextRange class

- Added the [ApiTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange.md) class to Spreadsheet API.
- Added the [ApiTextRange/AddHyperlink](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/AddHyperlink.md) method to Spreadsheet API.
- Added the [ApiTextRange/AddText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/AddText.md) method to Spreadsheet API.
- Added the [ApiTextRange/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/Delete.md) method to Spreadsheet API.
- Added the [ApiTextRange/ExpandTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/ExpandTo.md) method to Spreadsheet API.
- Added the [ApiTextRange/Find](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/Find.md) method to Spreadsheet API.
- Added the [ApiTextRange/GetAllParagraphs](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/GetAllParagraphs.md) method to Spreadsheet API.
- Added the [ApiTextRange/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/GetClassType.md) method to Spreadsheet API.
- Added the [ApiTextRange/GetEndPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/GetEndPos.md) method to Spreadsheet API.
- Added the [ApiTextRange/GetParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/GetParagraph.md) method to Spreadsheet API.
- Added the [ApiTextRange/GetRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/GetRange.md) method to Spreadsheet API.
- Added the [ApiTextRange/GetStartPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/GetStartPos.md) method to Spreadsheet API.
- Added the [ApiTextRange/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/GetText.md) method to Spreadsheet API.
- Added the [ApiTextRange/GetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/GetTextPr.md) method to Spreadsheet API.
- Added the [ApiTextRange/IntersectWith](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/IntersectWith.md) method to Spreadsheet API.
- Added the [ApiTextRange/MoveCursorToPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/MoveCursorToPos.md) method to Spreadsheet API.
- Added the [ApiTextRange/Replace](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/Replace.md) method to Spreadsheet API.
- Added the [ApiTextRange/Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/Select.md) method to Spreadsheet API.
- Added the [ApiTextRange/SetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/SetBold.md) method to Spreadsheet API.
- Added the [ApiTextRange/SetCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/SetCaps.md) method to Spreadsheet API.
- Added the [ApiTextRange/SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/SetColor.md) method to Spreadsheet API.
- Added the [ApiTextRange/SetDoubleStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/SetDoubleStrikeout.md) method to Spreadsheet API.
- Added the [ApiTextRange/SetEndPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/SetEndPos.md) method to Spreadsheet API.
- Added the [ApiTextRange/SetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/SetFontFamily.md) method to Spreadsheet API.
- Added the [ApiTextRange/SetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/SetFontSize.md) method to Spreadsheet API.
- Added the [ApiTextRange/SetHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/SetHighlight.md) method to Spreadsheet API.
- Added the [ApiTextRange/SetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/SetItalic.md) method to Spreadsheet API.
- Added the [ApiTextRange/SetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/SetLanguage.md) method to Spreadsheet API.
- Added the [ApiTextRange/SetSmallCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/SetSmallCaps.md) method to Spreadsheet API.
- Added the [ApiTextRange/SetSpacing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/SetSpacing.md) method to Spreadsheet API.
- Added the [ApiTextRange/SetStartPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/SetStartPos.md) method to Spreadsheet API.
- Added the [ApiTextRange/SetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/SetStrikeout.md) method to Spreadsheet API.
- Added the [ApiTextRange/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/SetText.md) method to Spreadsheet API.
- Added the [ApiTextRange/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/SetTextPr.md) method to Spreadsheet API.
- Added the [ApiTextRange/SetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/SetUnderline.md) method to Spreadsheet API.
- Added the [ApiTextRange/SetVertAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/SetVertAlign.md) method to Spreadsheet API.
- Added the [ApiTextRange/ToHtml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange/Methods/ToHtml.md) method to Spreadsheet API.

#### ApiTop10 methods

- Added the [ApiTop10/GetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetStopIfTrue.md) method to Spreadsheet API.
- Added the [ApiTop10/SetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetStopIfTrue.md) method to Spreadsheet API.

#### ApiUniqueValues methods

- Added the [ApiUniqueValues/GetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetStopIfTrue.md) method to Spreadsheet API.
- Added the [ApiUniqueValues/SetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetStopIfTrue.md) method to Spreadsheet API.

#### ApiWorkbook methods

- Added the [ApiWorkbook/BreakLink](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/BreakLink.md) method to Spreadsheet API.
- Added the [ApiWorkbook/Calculate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/Calculate.md) method to Spreadsheet API.
- Added the [ApiWorkbook/GetLinkSources](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/GetLinkSources.md) method to Spreadsheet API.
- Added the [ApiWorkbook/Redraw](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/Redraw.md) method to Spreadsheet API.

#### ApiWorksheet methods

- Added the [ApiWorksheet/GetHyperlinks](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/GetHyperlinks.md) method to Spreadsheet API.
- Added the [ApiWorksheet/GetPageSetup](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/GetPageSetup.md) method to Spreadsheet API.
- Added the [ApiWorksheet/GroupDrawings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/GroupDrawings.md) method to Spreadsheet API.

#### Spreadsheet types

- Added the [ChartTypeLegacy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ChartTypeLegacy.md) type to the simple type definitions.
- Added the [DrawingCellAnchor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/DrawingCellAnchor.md) type to the simple type definitions.
- Added the [LineCapType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/LineCapType.md) type to the simple type definitions.
- Added the [LineEndSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/LineEndSize.md) type to the simple type definitions.
- Added the [LineEndType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/LineEndType.md) type to the simple type definitions.
- Added the [LineJoinType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/LineJoinType.md) type to the simple type definitions.
- Added the [PaperSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/PaperSize.md) type to the simple type definitions.
- Added the [ShadowSettings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ShadowSettings.md) type to the simple type definitions.
- Added the [ShapesMergeOperation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ShapesMergeOperation.md) type to the simple type definitions.
- Added the [ShdType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ShdType.md) type to the simple type definitions.
- Added the [ToHtmlOptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ToHtmlOptions.md) type to the simple type definitions.

### Presentation methods

#### Api methods

- Added the [Api/CreateMath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateMath.md) method to Presentation API.
- Added the [Api/CreateShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateShadow.md) method to Presentation API.
- Added the [Api/CreateShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateShd.md) method to Presentation API.
- Added the [Api/CreateTablePr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateTablePr.md) method to Presentation API.
- Added the [Api/CreateTableRowPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateTableRowPr.md) method to Presentation API.
- Added the [Api/MergeShapes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/MergeShapes.md) method to Presentation API.

#### ApiBullet methods

- Added the [ApiBullet/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiBullet/Methods/ToJSON.md) method to Presentation API.

#### ApiChart methods

- Added the [ApiChart/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/GetDescription.md) method to Presentation API.
- Added the [ApiChart/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/GetFill.md) method to Presentation API.
- Added the [ApiChart/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/GetLine.md) method to Presentation API.
- Added the [ApiChart/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/GetLockAspect.md) method to Presentation API.
- Added the [ApiChart/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/GetShadow.md) method to Presentation API.
- Added the [ApiChart/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/GetTextRange.md) method to Presentation API.
- Added the [ApiChart/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/GetType.md) method to Presentation API.
- Added the [ApiChart/GetVisitor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/GetVisitor.md) method to Presentation API.
- Added the [ApiChart/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/HasTextContent.md) method to Presentation API.
- Added the [ApiChart/SetDataLabelsTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetDataLabelsTextPr.md) method to Presentation API.
- Added the [ApiChart/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetDescription.md) method to Presentation API.
- Added the [ApiChart/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetFill.md) method to Presentation API.
- Added the [ApiChart/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetLine.md) method to Presentation API.
- Added the [ApiChart/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetLockAspect.md) method to Presentation API.
- Added the [ApiChart/SetPointDataLabelTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetPointDataLabelTextPr.md) method to Presentation API.
- Added the [ApiChart/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetShadow.md) method to Presentation API.
- Added the [ApiChart/SetShowDataTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetShowDataTable.md) method to Presentation API.

#### ApiChartSeries methods

- Added the [ApiChartSeries/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChartSeries/Methods/GetType.md) method to Presentation API.

#### ApiColor methods

- Added the [ApiColor/GetTintAndShade](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiColor/Methods/GetTintAndShade.md) method to Presentation API.

#### ApiDocumentContent methods

- Added the [ApiDocumentContent/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDocumentContent/Methods/GetTextRange.md) method to Presentation API.

#### ApiDrawing methods

- Added the [ApiDrawing/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/GetDescription.md) method to Presentation API.
- Added the [ApiDrawing/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/GetFill.md) method to Presentation API.
- Added the [ApiDrawing/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/GetLine.md) method to Presentation API.
- Added the [ApiDrawing/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/GetLockAspect.md) method to Presentation API.
- Added the [ApiDrawing/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/GetShadow.md) method to Presentation API.
- Added the [ApiDrawing/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/GetTextRange.md) method to Presentation API.
- Added the [ApiDrawing/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/GetTitle.md) method to Presentation API.
- Added the [ApiDrawing/GetVisitor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/GetVisitor.md) method to Presentation API.
- Added the [ApiDrawing/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/HasTextContent.md) method to Presentation API.
- Added the [ApiDrawing/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/SetDescription.md) method to Presentation API.
- Added the [ApiDrawing/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/SetFill.md) method to Presentation API.
- Added the [ApiDrawing/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/SetLine.md) method to Presentation API.
- Added the [ApiDrawing/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/SetLockAspect.md) method to Presentation API.
- Added the [ApiDrawing/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/SetShadow.md) method to Presentation API.
- Added the [ApiDrawing/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/SetTitle.md) method to Presentation API.

#### ApiFill methods

- Added the [ApiFill/GetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiFill/Methods/GetColor.md) method to Presentation API.
- Added the [ApiFill/GetTransparent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiFill/Methods/GetTransparent.md) method to Presentation API.
- Added the [ApiFill/SetTransparent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiFill/Methods/SetTransparent.md) method to Presentation API.

#### ApiGeometry methods

- Added the [ApiGeometry/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGeometry/Methods/GetClassType.md) method to Presentation API.

#### ApiGroup methods

- Added the [ApiGroup/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGroup/Methods/GetDescription.md) method to Presentation API.
- Added the [ApiGroup/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGroup/Methods/GetFill.md) method to Presentation API.
- Added the [ApiGroup/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGroup/Methods/GetLine.md) method to Presentation API.
- Added the [ApiGroup/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGroup/Methods/GetLockAspect.md) method to Presentation API.
- Added the [ApiGroup/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGroup/Methods/GetShadow.md) method to Presentation API.
- Added the [ApiGroup/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGroup/Methods/GetTextRange.md) method to Presentation API.
- Added the [ApiGroup/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGroup/Methods/GetTitle.md) method to Presentation API.
- Added the [ApiGroup/GetVisitor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGroup/Methods/GetVisitor.md) method to Presentation API.
- Added the [ApiGroup/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGroup/Methods/HasTextContent.md) method to Presentation API.
- Added the [ApiGroup/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGroup/Methods/SetDescription.md) method to Presentation API.
- Added the [ApiGroup/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGroup/Methods/SetFill.md) method to Presentation API.
- Added the [ApiGroup/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGroup/Methods/SetLine.md) method to Presentation API.
- Added the [ApiGroup/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGroup/Methods/SetLockAspect.md) method to Presentation API.
- Added the [ApiGroup/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGroup/Methods/SetShadow.md) method to Presentation API.
- Added the [ApiGroup/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGroup/Methods/SetTitle.md) method to Presentation API.

#### ApiHyperlink methods

- Added the [ApiHyperlink/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiHyperlink/Methods/GetTextRange.md) method to Presentation API.

#### ApiImage methods

- Added the [ApiImage/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiImage/Methods/GetDescription.md) method to Presentation API.
- Added the [ApiImage/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiImage/Methods/GetFill.md) method to Presentation API.
- Added the [ApiImage/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiImage/Methods/GetLine.md) method to Presentation API.
- Added the [ApiImage/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiImage/Methods/GetLockAspect.md) method to Presentation API.
- Added the [ApiImage/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiImage/Methods/GetShadow.md) method to Presentation API.
- Added the [ApiImage/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiImage/Methods/GetTextRange.md) method to Presentation API.
- Added the [ApiImage/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiImage/Methods/GetTitle.md) method to Presentation API.
- Added the [ApiImage/GetVisitor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiImage/Methods/GetVisitor.md) method to Presentation API.
- Added the [ApiImage/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiImage/Methods/HasTextContent.md) method to Presentation API.
- Added the [ApiImage/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiImage/Methods/SetDescription.md) method to Presentation API.
- Added the [ApiImage/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiImage/Methods/SetFill.md) method to Presentation API.
- Added the [ApiImage/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiImage/Methods/SetLine.md) method to Presentation API.
- Added the [ApiImage/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiImage/Methods/SetLockAspect.md) method to Presentation API.
- Added the [ApiImage/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiImage/Methods/SetShadow.md) method to Presentation API.
- Added the [ApiImage/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiImage/Methods/SetTitle.md) method to Presentation API.

#### ApiLayout methods

- Added the [ApiLayout/GetBackground](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/GetBackground.md) method to Presentation API.
- Added the [ApiLayout/GetVisitor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/GetVisitor.md) method to Presentation API.
- Added the [ApiLayout/Search](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/Search.md) method to Presentation API.

#### ApiMaster methods

- Added the [ApiMaster/GetBackground](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/GetBackground.md) method to Presentation API.
- Added the [ApiMaster/GetVisitor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/GetVisitor.md) method to Presentation API.
- Added the [ApiMaster/Search](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/Search.md) method to Presentation API.

#### ApiMath class

- Added the [ApiMath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMath.md) class to Presentation API.
- Added the [ApiMath/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMath/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiMath/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMath/Methods/GetText.md) method to Presentation API.

#### ApiNotesPage methods

- Added the [ApiNotesPage/GetTheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiNotesPage/Methods/GetTheme.md) method to Presentation API.

#### ApiOleObject methods

- Added the [ApiOleObject/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/GetDescription.md) method to Presentation API.
- Added the [ApiOleObject/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/GetFill.md) method to Presentation API.
- Added the [ApiOleObject/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/GetLine.md) method to Presentation API.
- Added the [ApiOleObject/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/GetLockAspect.md) method to Presentation API.
- Added the [ApiOleObject/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/GetShadow.md) method to Presentation API.
- Added the [ApiOleObject/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/GetTextRange.md) method to Presentation API.
- Added the [ApiOleObject/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/GetTitle.md) method to Presentation API.
- Added the [ApiOleObject/GetVisitor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/GetVisitor.md) method to Presentation API.
- Added the [ApiOleObject/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/HasTextContent.md) method to Presentation API.
- Added the [ApiOleObject/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/SetDescription.md) method to Presentation API.
- Added the [ApiOleObject/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/SetFill.md) method to Presentation API.
- Added the [ApiOleObject/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/SetLine.md) method to Presentation API.
- Added the [ApiOleObject/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/SetLockAspect.md) method to Presentation API.
- Added the [ApiOleObject/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/SetShadow.md) method to Presentation API.
- Added the [ApiOleObject/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/SetTitle.md) method to Presentation API.

#### ApiParagraph methods

- Added the [ApiParagraph/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/GetTextRange.md) method to Presentation API.
- Added the [ApiParagraph/IsEmpty](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/IsEmpty.md) method to Presentation API.
- Added the [ApiParagraph/SetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/SetLanguage.md) method to Presentation API.
- Added the [ApiParagraph/ToHtml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/ToHtml.md) method to Presentation API.

#### ApiPresentation methods

- Added the [ApiPresentation/EnterText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/EnterText.md) method to Presentation API.
- Added the [ApiPresentation/GetActiveShape](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetActiveShape.md) method to Presentation API.
- Added the [ApiPresentation/GetActiveTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetActiveTable.md) method to Presentation API.
- Added the [ApiPresentation/GetCurrentSentence](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetCurrentSentence.md) method to Presentation API.
- Added the [ApiPresentation/GetCurrentWord](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetCurrentWord.md) method to Presentation API.
- Added the [ApiPresentation/GetSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetSelection.md) method to Presentation API.
- Added the [ApiPresentation/GetStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetStyle.md) method to Presentation API.
- Added the [ApiPresentation/GetVisitor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetVisitor.md) method to Presentation API.
- Added the [ApiPresentation/InsertFromFile](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/InsertFromFile.md) method to Presentation API.
- Added the [ApiPresentation/InsertParagraphBreak](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/InsertParagraphBreak.md) method to Presentation API.
- Added the [ApiPresentation/MoveCursorDown](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/MoveCursorDown.md) method to Presentation API.
- Added the [ApiPresentation/MoveCursorLeft](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/MoveCursorLeft.md) method to Presentation API.
- Added the [ApiPresentation/MoveCursorRight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/MoveCursorRight.md) method to Presentation API.
- Added the [ApiPresentation/MoveCursorUp](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/MoveCursorUp.md) method to Presentation API.
- Added the [ApiPresentation/MoveToNextCell](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/MoveToNextCell.md) method to Presentation API.
- Added the [ApiPresentation/MoveToPrevCell](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/MoveToPrevCell.md) method to Presentation API.
- Added the [ApiPresentation/ReplaceCurrentSentence](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/ReplaceCurrentSentence.md) method to Presentation API.
- Added the [ApiPresentation/ReplaceCurrentWord](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/ReplaceCurrentWord.md) method to Presentation API.
- Added the [ApiPresentation/Search](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/Search.md) method to Presentation API.
- Added the [ApiPresentation/SearchAndReplace](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/SearchAndReplace.md) method to Presentation API.
- Added the [ApiPresentation/SelectCurrentSentence](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/SelectCurrentSentence.md) method to Presentation API.
- Added the [ApiPresentation/SelectCurrentWord](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/SelectCurrentWord.md) method to Presentation API.

#### ApiPresentationVisitor class

- Added the [ApiPresentationVisitor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentationVisitor.md) class to Presentation API.
- Added the [ApiPresentationVisitor/Stop](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentationVisitor/Methods/Stop.md) method to Presentation API.
- Added the [ApiPresentationVisitor/Traverse](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentationVisitor/Methods/Traverse.md) method to Presentation API.

#### ApiRun methods

- Added the [ApiRun/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiRun/Methods/GetTextRange.md) method to Presentation API.
- Added the [ApiRun/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiRun/Methods/SetText.md) method to Presentation API.

#### ApiSelection methods

- Added the [ApiSelection/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSelection/Methods/GetTextRange.md) method to Presentation API.

#### ApiShadow class

- Added the [ApiShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShadow.md) class to Presentation API.
- Added the [ApiShadow/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShadow/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiShadow/GetSettings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShadow/Methods/GetSettings.md) method to Presentation API.

#### ApiShape methods

- Added the [ApiShape/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/GetDescription.md) method to Presentation API.
- Added the [ApiShape/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/GetLockAspect.md) method to Presentation API.
- Added the [ApiShape/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/GetShadow.md) method to Presentation API.
- Added the [ApiShape/GetTextFit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/GetTextFit.md) method to Presentation API.
- Added the [ApiShape/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/GetTextRange.md) method to Presentation API.
- Added the [ApiShape/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/GetTitle.md) method to Presentation API.
- Added the [ApiShape/GetVerticalTextAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/GetVerticalTextAlign.md) method to Presentation API.
- Added the [ApiShape/GetVisitor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/GetVisitor.md) method to Presentation API.
- Added the [ApiShape/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/HasTextContent.md) method to Presentation API.
- Added the [ApiShape/RecalculateAutoFit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/RecalculateAutoFit.md) method to Presentation API.
- Added the [ApiShape/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/SetDescription.md) method to Presentation API.
- Added the [ApiShape/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/SetLockAspect.md) method to Presentation API.
- Added the [ApiShape/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/SetShadow.md) method to Presentation API.
- Added the [ApiShape/SetTextFit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/SetTextFit.md) method to Presentation API.
- Added the [ApiShape/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/SetTitle.md) method to Presentation API.

#### ApiShd class

- Added the [ApiShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShd.md) class to Presentation API.
- Added the [ApiShd/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShd/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiShd/GetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShd/Methods/GetColor.md) method to Presentation API.
- Added the [ApiShd/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShd/Methods/GetType.md) method to Presentation API.

#### ApiSlide methods

- Added the [ApiSlide/GetBackground](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/GetBackground.md) method to Presentation API.
- Added the [ApiSlide/GetVisitor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/GetVisitor.md) method to Presentation API.
- Added the [ApiSlide/Search](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/Search.md) method to Presentation API.

#### ApiSmartArt methods

- Added the [ApiSmartArt/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSmartArt/Methods/GetDescription.md) method to Presentation API.
- Added the [ApiSmartArt/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSmartArt/Methods/GetFill.md) method to Presentation API.
- Added the [ApiSmartArt/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSmartArt/Methods/GetLine.md) method to Presentation API.
- Added the [ApiSmartArt/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSmartArt/Methods/GetLockAspect.md) method to Presentation API.
- Added the [ApiSmartArt/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSmartArt/Methods/GetShadow.md) method to Presentation API.
- Added the [ApiSmartArt/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSmartArt/Methods/GetTextRange.md) method to Presentation API.
- Added the [ApiSmartArt/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSmartArt/Methods/GetTitle.md) method to Presentation API.
- Added the [ApiSmartArt/GetVisitor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSmartArt/Methods/GetVisitor.md) method to Presentation API.
- Added the [ApiSmartArt/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSmartArt/Methods/HasTextContent.md) method to Presentation API.
- Added the [ApiSmartArt/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSmartArt/Methods/SetDescription.md) method to Presentation API.
- Added the [ApiSmartArt/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSmartArt/Methods/SetFill.md) method to Presentation API.
- Added the [ApiSmartArt/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSmartArt/Methods/SetLine.md) method to Presentation API.
- Added the [ApiSmartArt/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSmartArt/Methods/SetLockAspect.md) method to Presentation API.
- Added the [ApiSmartArt/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSmartArt/Methods/SetShadow.md) method to Presentation API.
- Added the [ApiSmartArt/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSmartArt/Methods/SetTitle.md) method to Presentation API.

#### ApiStroke methods

- Added the [ApiStroke/GetBeginArrow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiStroke/Methods/GetBeginArrow.md) method to Presentation API.
- Added the [ApiStroke/GetCapType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiStroke/Methods/GetCapType.md) method to Presentation API.
- Added the [ApiStroke/GetEndArrow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiStroke/Methods/GetEndArrow.md) method to Presentation API.
- Added the [ApiStroke/GetJoinType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiStroke/Methods/GetJoinType.md) method to Presentation API.
- Added the [ApiStroke/SetBeginArrow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiStroke/Methods/SetBeginArrow.md) method to Presentation API.
- Added the [ApiStroke/SetCapType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiStroke/Methods/SetCapType.md) method to Presentation API.
- Added the [ApiStroke/SetEndArrow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiStroke/Methods/SetEndArrow.md) method to Presentation API.
- Added the [ApiStroke/SetJoinType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiStroke/Methods/SetJoinType.md) method to Presentation API.

#### ApiStyle class

- Added the [ApiStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiStyle.md) class to Presentation API.
- Added the [ApiStyle/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiStyle/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiStyle/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiStyle/Methods/GetName.md) method to Presentation API.
- Added the [ApiStyle/GetTablePr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiStyle/Methods/GetTablePr.md) method to Presentation API.
- Added the [ApiStyle/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiStyle/Methods/GetType.md) method to Presentation API.
- Added the [ApiStyle/SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiStyle/Methods/SetName.md) method to Presentation API.
- Added the [ApiStyle/SetTablePr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiStyle/Methods/SetTablePr.md) method to Presentation API.

#### ApiTable methods

- Added the [ApiTable/AddColumns](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/AddColumns.md) method to Presentation API.
- Added the [ApiTable/AddElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/AddElement.md) method to Presentation API.
- Added the [ApiTable/AddRows](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/AddRows.md) method to Presentation API.
- Added the [ApiTable/Clear](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/Clear.md) method to Presentation API.
- Added the [ApiTable/GetCell](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/GetCell.md) method to Presentation API.
- Added the [ApiTable/GetColumnsCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/GetColumnsCount.md) method to Presentation API.
- Added the [ApiTable/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/GetDescription.md) method to Presentation API.
- Added the [ApiTable/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/GetFill.md) method to Presentation API.
- Added the [ApiTable/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/GetLine.md) method to Presentation API.
- Added the [ApiTable/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/GetLockAspect.md) method to Presentation API.
- Added the [ApiTable/GetRowsCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/GetRowsCount.md) method to Presentation API.
- Added the [ApiTable/GetSelectedCells](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/GetSelectedCells.md) method to Presentation API.
- Added the [ApiTable/GetSelectedColumnsCells](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/GetSelectedColumnsCells.md) method to Presentation API.
- Added the [ApiTable/GetSelectedRows](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/GetSelectedRows.md) method to Presentation API.
- Added the [ApiTable/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/GetShadow.md) method to Presentation API.
- Added the [ApiTable/GetTableDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/GetTableDescription.md) method to Presentation API.
- Added the [ApiTable/GetTableLook](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/GetTableLook.md) method to Presentation API.
- Added the [ApiTable/GetTableTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/GetTableTitle.md) method to Presentation API.
- Added the [ApiTable/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/GetTextRange.md) method to Presentation API.
- Added the [ApiTable/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/GetTitle.md) method to Presentation API.
- Added the [ApiTable/GetVisitor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/GetVisitor.md) method to Presentation API.
- Added the [ApiTable/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/HasTextContent.md) method to Presentation API.
- Added the [ApiTable/SelectRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/SelectRange.md) method to Presentation API.
- Added the [ApiTable/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/SetBackgroundColor.md) method to Presentation API.
- Added the [ApiTable/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/SetDescription.md) method to Presentation API.
- Added the [ApiTable/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/SetFill.md) method to Presentation API.
- Added the [ApiTable/SetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/SetHeight.md) method to Presentation API.
- Added the [ApiTable/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/SetLine.md) method to Presentation API.
- Added the [ApiTable/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/SetLockAspect.md) method to Presentation API.
- Added the [ApiTable/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/SetShadow.md) method to Presentation API.
- Added the [ApiTable/SetStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/SetStyle.md) method to Presentation API.
- Added the [ApiTable/SetTableDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/SetTableDescription.md) method to Presentation API.
- Added the [ApiTable/SetTableTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/SetTableTitle.md) method to Presentation API.
- Added the [ApiTable/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/SetTitle.md) method to Presentation API.

#### ApiTableCell methods

- Added the [ApiTableCell/AddColumns](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableCell/Methods/AddColumns.md) method to Presentation API.
- Added the [ApiTableCell/AddRows](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableCell/Methods/AddRows.md) method to Presentation API.
- Added the [ApiTableCell/Clear](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableCell/Methods/Clear.md) method to Presentation API.
- Added the [ApiTableCell/GetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableCell/Methods/GetBackgroundColor.md) method to Presentation API.
- Added the [ApiTableCell/GetIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableCell/Methods/GetIndex.md) method to Presentation API.
- Added the [ApiTableCell/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableCell/Methods/GetInternalId.md) method to Presentation API.
- Added the [ApiTableCell/GetNext](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableCell/Methods/GetNext.md) method to Presentation API.
- Added the [ApiTableCell/GetParentRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableCell/Methods/GetParentRow.md) method to Presentation API.
- Added the [ApiTableCell/GetParentTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableCell/Methods/GetParentTable.md) method to Presentation API.
- Added the [ApiTableCell/GetPrevious](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableCell/Methods/GetPrevious.md) method to Presentation API.
- Added the [ApiTableCell/GetRowIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableCell/Methods/GetRowIndex.md) method to Presentation API.
- Added the [ApiTableCell/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableCell/Methods/GetTextRange.md) method to Presentation API.
- Added the [ApiTableCell/RemoveColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableCell/Methods/RemoveColumn.md) method to Presentation API.
- Added the [ApiTableCell/RemoveRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableCell/Methods/RemoveRow.md) method to Presentation API.
- Added the [ApiTableCell/Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableCell/Methods/Select.md) method to Presentation API.
- Added the [ApiTableCell/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableCell/Methods/SetBackgroundColor.md) method to Presentation API.
- Added the [ApiTableCell/SetColumnBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableCell/Methods/SetColumnBackgroundColor.md) method to Presentation API.
- Added the [ApiTableCell/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableCell/Methods/SetTextPr.md) method to Presentation API.

#### ApiTablePr class

- Added the [ApiTablePr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTablePr.md) class to Presentation API.
- Added the [ApiTablePr/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTablePr/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiTablePr/SetShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTablePr/Methods/SetShd.md) method to Presentation API.
- Added the [ApiTablePr/SetTableBorderAll](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTablePr/Methods/SetTableBorderAll.md) method to Presentation API.
- Added the [ApiTablePr/SetTableBorderBottom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTablePr/Methods/SetTableBorderBottom.md) method to Presentation API.
- Added the [ApiTablePr/SetTableBorderInsideH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTablePr/Methods/SetTableBorderInsideH.md) method to Presentation API.
- Added the [ApiTablePr/SetTableBorderInsideV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTablePr/Methods/SetTableBorderInsideV.md) method to Presentation API.
- Added the [ApiTablePr/SetTableBorderLeft](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTablePr/Methods/SetTableBorderLeft.md) method to Presentation API.
- Added the [ApiTablePr/SetTableBorderRight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTablePr/Methods/SetTableBorderRight.md) method to Presentation API.
- Added the [ApiTablePr/SetTableBorderTop](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTablePr/Methods/SetTableBorderTop.md) method to Presentation API.
- Added the [ApiTablePr/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTablePr/Methods/ToJSON.md) method to Presentation API.

#### ApiTableRow methods

- Added the [ApiTableRow/AddRows](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableRow/Methods/AddRows.md) method to Presentation API.
- Added the [ApiTableRow/Clear](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableRow/Methods/Clear.md) method to Presentation API.
- Added the [ApiTableRow/GetIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableRow/Methods/GetIndex.md) method to Presentation API.
- Added the [ApiTableRow/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableRow/Methods/GetInternalId.md) method to Presentation API.
- Added the [ApiTableRow/GetNext](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableRow/Methods/GetNext.md) method to Presentation API.
- Added the [ApiTableRow/GetParentTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableRow/Methods/GetParentTable.md) method to Presentation API.
- Added the [ApiTableRow/GetPrevious](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableRow/Methods/GetPrevious.md) method to Presentation API.
- Added the [ApiTableRow/MergeCells](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableRow/Methods/MergeCells.md) method to Presentation API.
- Added the [ApiTableRow/Remove](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableRow/Methods/Remove.md) method to Presentation API.
- Added the [ApiTableRow/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableRow/Methods/SetBackgroundColor.md) method to Presentation API.
- Added the [ApiTableRow/SetRowPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableRow/Methods/SetRowPr.md) method to Presentation API.
- Added the [ApiTableRow/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableRow/Methods/SetTextPr.md) method to Presentation API.
- Added the [ApiTableRow/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableRow/Methods/ToJSON.md) method to Presentation API.

#### ApiTableRowPr class

- Added the [ApiTableRowPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableRowPr.md) class to Presentation API.
- Added the [ApiTableRowPr/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableRowPr/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiTableRowPr/SetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableRowPr/Methods/SetHeight.md) method to Presentation API.
- Added the [ApiTableRowPr/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableRowPr/Methods/ToJSON.md) method to Presentation API.

#### ApiTableStylePr class

- Added the [ApiTableStylePr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableStylePr.md) class to Presentation API.
- Added the [ApiTableStylePr/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableStylePr/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiTableStylePr/GetTablePr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableStylePr/Methods/GetTablePr.md) method to Presentation API.
- Added the [ApiTableStylePr/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableStylePr/Methods/GetType.md) method to Presentation API.
- Added the [ApiTableStylePr/SetTablePr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTableStylePr/Methods/SetTablePr.md) method to Presentation API.

#### ApiTextPr methods

- Added the [ApiTextPr/SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextPr/Methods/SetColor.md) method to Presentation API.
- Added the [ApiTextPr/SetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextPr/Methods/SetLanguage.md) method to Presentation API.

#### ApiTextRange class

- Added the [ApiTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange.md) class to Presentation API.
- Added the [ApiTextRange/AddHyperlink](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/AddHyperlink.md) method to Presentation API.
- Added the [ApiTextRange/AddText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/AddText.md) method to Presentation API.
- Added the [ApiTextRange/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/Delete.md) method to Presentation API.
- Added the [ApiTextRange/ExpandTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/ExpandTo.md) method to Presentation API.
- Added the [ApiTextRange/Find](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/Find.md) method to Presentation API.
- Added the [ApiTextRange/GetAllParagraphs](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/GetAllParagraphs.md) method to Presentation API.
- Added the [ApiTextRange/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiTextRange/GetEndPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/GetEndPos.md) method to Presentation API.
- Added the [ApiTextRange/GetParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/GetParagraph.md) method to Presentation API.
- Added the [ApiTextRange/GetRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/GetRange.md) method to Presentation API.
- Added the [ApiTextRange/GetStartPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/GetStartPos.md) method to Presentation API.
- Added the [ApiTextRange/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/GetText.md) method to Presentation API.
- Added the [ApiTextRange/GetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/GetTextPr.md) method to Presentation API.
- Added the [ApiTextRange/IntersectWith](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/IntersectWith.md) method to Presentation API.
- Added the [ApiTextRange/MoveCursorToPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/MoveCursorToPos.md) method to Presentation API.
- Added the [ApiTextRange/Replace](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/Replace.md) method to Presentation API.
- Added the [ApiTextRange/Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/Select.md) method to Presentation API.
- Added the [ApiTextRange/SetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/SetBold.md) method to Presentation API.
- Added the [ApiTextRange/SetCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/SetCaps.md) method to Presentation API.
- Added the [ApiTextRange/SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/SetColor.md) method to Presentation API.
- Added the [ApiTextRange/SetDoubleStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/SetDoubleStrikeout.md) method to Presentation API.
- Added the [ApiTextRange/SetEndPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/SetEndPos.md) method to Presentation API.
- Added the [ApiTextRange/SetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/SetFontFamily.md) method to Presentation API.
- Added the [ApiTextRange/SetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/SetFontSize.md) method to Presentation API.
- Added the [ApiTextRange/SetHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/SetHighlight.md) method to Presentation API.
- Added the [ApiTextRange/SetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/SetItalic.md) method to Presentation API.
- Added the [ApiTextRange/SetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/SetLanguage.md) method to Presentation API.
- Added the [ApiTextRange/SetSmallCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/SetSmallCaps.md) method to Presentation API.
- Added the [ApiTextRange/SetSpacing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/SetSpacing.md) method to Presentation API.
- Added the [ApiTextRange/SetStartPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/SetStartPos.md) method to Presentation API.
- Added the [ApiTextRange/SetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/SetStrikeout.md) method to Presentation API.
- Added the [ApiTextRange/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/SetText.md) method to Presentation API.
- Added the [ApiTextRange/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/SetTextPr.md) method to Presentation API.
- Added the [ApiTextRange/SetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/SetUnderline.md) method to Presentation API.
- Added the [ApiTextRange/SetVertAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/SetVertAlign.md) method to Presentation API.
- Added the [ApiTextRange/ToHtml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextRange/Methods/ToHtml.md) method to Presentation API.

#### ApiThemeColorScheme methods

- Added the [ApiThemeColorScheme/GetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeColorScheme/Methods/GetColor.md) method to Presentation API.
- Added the [ApiThemeColorScheme/GetSchemeName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeColorScheme/Methods/GetSchemeName.md) method to Presentation API.

#### ApiThemeFontScheme methods

- Added the [ApiThemeFontScheme/GetMajorFont](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeFontScheme/Methods/GetMajorFont.md) method to Presentation API.
- Added the [ApiThemeFontScheme/GetMinorFont](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeFontScheme/Methods/GetMinorFont.md) method to Presentation API.
- Added the [ApiThemeFontScheme/GetSchemeName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeFontScheme/Methods/GetSchemeName.md) method to Presentation API.

#### Presentation types

- Added the [BorderType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/BorderType.md) type to the simple type definitions.
- Added the [ChartTypeLegacy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/ChartTypeLegacy.md) type to the simple type definitions.
- Added the [LineCapType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/LineCapType.md) type to the simple type definitions.
- Added the [LineEndSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/LineEndSize.md) type to the simple type definitions.
- Added the [LineEndType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/LineEndType.md) type to the simple type definitions.
- Added the [LineJoinType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/LineJoinType.md) type to the simple type definitions.
- Added the [ShadowSettings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/ShadowSettings.md) type to the simple type definitions.
- Added the [ShapesMergeOperation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/ShapesMergeOperation.md) type to the simple type definitions.
- Added the [StyleType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/StyleType.md) type to the simple type definitions.
- Added the [TableLook](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/TableLook.md) type to the simple type definitions.
- Added the [TableStyleOverrideType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/TableStyleOverrideType.md) type to the simple type definitions.
- Added the [TextFitType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/TextFitType.md) type to the simple type definitions.
- Added the [ThemeFontScript](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/ThemeFontScript.md) type to the simple type definitions.
- Added the [ToHtmlOptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/ToHtmlOptions.md) type to the simple type definitions.

### PDF methods

#### Api methods

- Added the [Api/CreateButtonField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateButtonField.md) method to PDF API.
- Added the [Api/CreateGoToAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateGoToAction.md) method to PDF API.
- Added the [Api/CreateHideShowFormsAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateHideShowFormsAction.md) method to PDF API.
- Added the [Api/CreateImageStampAnnot](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateImageStampAnnot.md) method to PDF API.
- Added the [Api/CreateJsAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateJsAction.md) method to PDF API.
- Added the [Api/CreateLinkAnnot](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateLinkAnnot.md) method to PDF API.
- Added the [Api/CreateMath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateMath.md) method to PDF API.
- Added the [Api/CreateNamedAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateNamedAction.md) method to PDF API.
- Added the [Api/CreateResetFormsAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateResetFormsAction.md) method to PDF API.
- Added the [Api/CreateShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateShadow.md) method to PDF API.
- Added the [Api/CreateShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateShd.md) method to PDF API.
- Added the [Api/CreateSignatureField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateSignatureField.md) method to PDF API.
- Added the [Api/CreateTableRowPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateTableRowPr.md) method to PDF API.
- Added the [Api/CreateUriAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateUriAction.md) method to PDF API.
- Added the [Api/MergeShapes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/MergeShapes.md) method to PDF API.

#### ApiActionCollection class

- Added the [ApiActionCollection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection.md) class to PDF API.
- Added the [ApiActionCollection/GetCalculate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/GetCalculate.md) method to PDF API.
- Added the [ApiActionCollection/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/GetClassType.md) method to PDF API.
- Added the [ApiActionCollection/GetFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/GetFormat.md) method to PDF API.
- Added the [ApiActionCollection/GetKeystroke](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/GetKeystroke.md) method to PDF API.
- Added the [ApiActionCollection/GetMouseDown](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/GetMouseDown.md) method to PDF API.
- Added the [ApiActionCollection/GetMouseEnter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/GetMouseEnter.md) method to PDF API.
- Added the [ApiActionCollection/GetMouseExit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/GetMouseExit.md) method to PDF API.
- Added the [ApiActionCollection/GetMouseUp](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/GetMouseUp.md) method to PDF API.
- Added the [ApiActionCollection/GetOnBlur](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/GetOnBlur.md) method to PDF API.
- Added the [ApiActionCollection/GetOnFocus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/GetOnFocus.md) method to PDF API.
- Added the [ApiActionCollection/GetValidate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/GetValidate.md) method to PDF API.
- Added the [ApiActionCollection/SetCalculate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/SetCalculate.md) method to PDF API.
- Added the [ApiActionCollection/SetFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/SetFormat.md) method to PDF API.
- Added the [ApiActionCollection/SetKeystroke](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/SetKeystroke.md) method to PDF API.
- Added the [ApiActionCollection/SetMouseDown](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/SetMouseDown.md) method to PDF API.
- Added the [ApiActionCollection/SetMouseEnter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/SetMouseEnter.md) method to PDF API.
- Added the [ApiActionCollection/SetMouseExit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/SetMouseExit.md) method to PDF API.
- Added the [ApiActionCollection/SetMouseUp](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/SetMouseUp.md) method to PDF API.
- Added the [ApiActionCollection/SetOnBlur](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/SetOnBlur.md) method to PDF API.
- Added the [ApiActionCollection/SetOnFocus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/SetOnFocus.md) method to PDF API.
- Added the [ApiActionCollection/SetValidate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection/Methods/SetValidate.md) method to PDF API.

#### ApiBaseAction class

- Added the [ApiBaseAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAction.md) class to PDF API.
- Added the [ApiBaseAction/GetNext](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAction/Methods/GetNext.md) method to PDF API.
- Added the [ApiBaseAction/SetNext](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAction/Methods/SetNext.md) method to PDF API.

#### ApiBaseWidget methods

- Added the [ApiBaseWidget/GetActions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/GetActions.md) method to PDF API.
- Added the [ApiBaseWidget/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/GetParent.md) method to PDF API.
- Added the [ApiBaseWidget/GetTextAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/GetTextAlign.md) method to PDF API.
- Added the [ApiBaseWidget/SetTextAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/SetTextAlign.md) method to PDF API.

#### ApiBullet methods

- Added the [ApiBullet/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBullet/Methods/ToJSON.md) method to PDF API.

#### ApiButtonWidget methods

- Added the [ApiButtonWidget/GetActions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetActions.md) method to PDF API.
- Added the [ApiButtonWidget/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetParent.md) method to PDF API.
- Added the [ApiButtonWidget/GetTextAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetTextAlign.md) method to PDF API.
- Added the [ApiButtonWidget/SetTextAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetTextAlign.md) method to PDF API.

#### ApiChart methods

- Added the [ApiChart/Fill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/Fill.md) method to PDF API.
- Added the [ApiChart/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/GetDescription.md) method to PDF API.
- Added the [ApiChart/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/GetFill.md) method to PDF API.
- Added the [ApiChart/GetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/GetFlipH.md) method to PDF API.
- Added the [ApiChart/GetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/GetFlipV.md) method to PDF API.
- Added the [ApiChart/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/GetLine.md) method to PDF API.
- Added the [ApiChart/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/GetLockAspect.md) method to PDF API.
- Added the [ApiChart/GetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/GetLockValue.md) method to PDF API.
- Added the [ApiChart/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/GetName.md) method to PDF API.
- Added the [ApiChart/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/GetShadow.md) method to PDF API.
- Added the [ApiChart/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/GetTextRange.md) method to PDF API.
- Added the [ApiChart/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/GetType.md) method to PDF API.
- Added the [ApiChart/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/HasTextContent.md) method to PDF API.
- Added the [ApiChart/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetDescription.md) method to PDF API.
- Added the [ApiChart/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetFill.md) method to PDF API.
- Added the [ApiChart/SetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetFlipH.md) method to PDF API.
- Added the [ApiChart/SetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetFlipV.md) method to PDF API.
- Added the [ApiChart/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetLine.md) method to PDF API.
- Added the [ApiChart/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetLockAspect.md) method to PDF API.
- Added the [ApiChart/SetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetLockValue.md) method to PDF API.
- Added the [ApiChart/SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetName.md) method to PDF API.
- Added the [ApiChart/SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetOutLine.md) method to PDF API.
- Added the [ApiChart/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetShadow.md) method to PDF API.
- Added the [ApiChart/SetShowDataTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetShowDataTable.md) method to PDF API.
- Added the [ApiChart/Unselect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/Unselect.md) method to PDF API.

#### ApiChartSeries methods

- Added the [ApiChartSeries/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChartSeries/Methods/GetType.md) method to PDF API.

#### ApiCheckboxWidget methods

- Added the [ApiCheckboxWidget/GetActions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxWidget/Methods/GetActions.md) method to PDF API.
- Added the [ApiCheckboxWidget/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxWidget/Methods/GetParent.md) method to PDF API.
- Added the [ApiCheckboxWidget/GetTextAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxWidget/Methods/GetTextAlign.md) method to PDF API.
- Added the [ApiCheckboxWidget/SetTextAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxWidget/Methods/SetTextAlign.md) method to PDF API.

#### ApiColor methods

- Added the [ApiColor/GetTintAndShade](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor/Methods/GetTintAndShade.md) method to PDF API.

#### ApiComboboxField methods

- Added the [ApiComboboxField/GetFormattedValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetFormattedValue.md) method to PDF API.
- Added the [ApiComboboxField/GetPlaceholder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetPlaceholder.md) method to PDF API.
- Added the [ApiComboboxField/GetRegularExp](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetRegularExp.md) method to PDF API.
- Added the [ApiComboboxField/SetPlaceholder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetPlaceholder.md) method to PDF API.

#### ApiDocument methods

- Added the [ApiDocument/GetCalculateOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetCalculateOrder.md) method to PDF API.
- Added the [ApiDocument/GetSelectedText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetSelectedText.md) method to PDF API.
- Added the [ApiDocument/GetSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetSelection.md) method to PDF API.
- Added the [ApiDocument/GetSelectionQuads](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetSelectionQuads.md) method to PDF API.
- Added the [ApiDocument/GetStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetStyle.md) method to PDF API.
- Added the [ApiDocument/Merge](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/Merge.md) method to PDF API.
- Added the [ApiDocument/SetCalculateOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/SetCalculateOrder.md) method to PDF API.
- Added the [ApiDocument/SetSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/SetSelection.md) method to PDF API.
- Added the [ApiDocument/Split](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/Split.md) method to PDF API.

#### ApiDocumentContent methods

- Added the [ApiDocumentContent/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/GetTextRange.md) method to PDF API.

#### ApiDrawing methods

- Added the [ApiDrawing/Fill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/Fill.md) method to PDF API.
- Added the [ApiDrawing/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/GetDescription.md) method to PDF API.
- Added the [ApiDrawing/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/GetFill.md) method to PDF API.
- Added the [ApiDrawing/GetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/GetFlipH.md) method to PDF API.
- Added the [ApiDrawing/GetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/GetFlipV.md) method to PDF API.
- Added the [ApiDrawing/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/GetLine.md) method to PDF API.
- Added the [ApiDrawing/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/GetLockAspect.md) method to PDF API.
- Added the [ApiDrawing/GetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/GetLockValue.md) method to PDF API.
- Added the [ApiDrawing/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/GetName.md) method to PDF API.
- Added the [ApiDrawing/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/GetShadow.md) method to PDF API.
- Added the [ApiDrawing/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/GetTextRange.md) method to PDF API.
- Added the [ApiDrawing/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/GetTitle.md) method to PDF API.
- Added the [ApiDrawing/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/HasTextContent.md) method to PDF API.
- Added the [ApiDrawing/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/SetDescription.md) method to PDF API.
- Added the [ApiDrawing/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/SetFill.md) method to PDF API.
- Added the [ApiDrawing/SetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/SetFlipH.md) method to PDF API.
- Added the [ApiDrawing/SetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/SetFlipV.md) method to PDF API.
- Added the [ApiDrawing/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/SetLine.md) method to PDF API.
- Added the [ApiDrawing/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/SetLockAspect.md) method to PDF API.
- Added the [ApiDrawing/SetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/SetLockValue.md) method to PDF API.
- Added the [ApiDrawing/SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/SetName.md) method to PDF API.
- Added the [ApiDrawing/SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/SetOutLine.md) method to PDF API.
- Added the [ApiDrawing/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/SetShadow.md) method to PDF API.
- Added the [ApiDrawing/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/SetTitle.md) method to PDF API.
- Added the [ApiDrawing/Unselect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/Unselect.md) method to PDF API.

#### ApiFill methods

- Added the [ApiFill/GetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiFill/Methods/GetColor.md) method to PDF API.
- Added the [ApiFill/GetTransparent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiFill/Methods/GetTransparent.md) method to PDF API.
- Added the [ApiFill/SetTransparent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiFill/Methods/SetTransparent.md) method to PDF API.

#### ApiFreeTextAnnotation methods

- Added the [ApiFreeTextAnnotation/GetEndStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiFreeTextAnnotation/Methods/GetEndStyle.md) method to PDF API.
- Added the [ApiFreeTextAnnotation/SetEndStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiFreeTextAnnotation/Methods/SetEndStyle.md) method to PDF API.

#### ApiGeometry methods

- Added the [ApiGeometry/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGeometry/Methods/GetClassType.md) method to PDF API.

#### ApiGoToAction class

- Added the [ApiGoToAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGoToAction.md) class to PDF API.
- Added the [ApiGoToAction/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGoToAction/Methods/GetClassType.md) method to PDF API.
- Added the [ApiGoToAction/GetPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGoToAction/Methods/GetPage.md) method to PDF API.
- Added the [ApiGoToAction/GetRect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGoToAction/Methods/GetRect.md) method to PDF API.
- Added the [ApiGoToAction/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGoToAction/Methods/GetType.md) method to PDF API.
- Added the [ApiGoToAction/GetZoom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGoToAction/Methods/GetZoom.md) method to PDF API.
- Added the [ApiGoToAction/SetPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGoToAction/Methods/SetPage.md) method to PDF API.
- Added the [ApiGoToAction/SetRect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGoToAction/Methods/SetRect.md) method to PDF API.
- Added the [ApiGoToAction/SetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGoToAction/Methods/SetType.md) method to PDF API.
- Added the [ApiGoToAction/SetZoom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGoToAction/Methods/SetZoom.md) method to PDF API.

#### ApiGroup methods

- Added the [ApiGroup/Fill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/Fill.md) method to PDF API.
- Added the [ApiGroup/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/GetDescription.md) method to PDF API.
- Added the [ApiGroup/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/GetFill.md) method to PDF API.
- Added the [ApiGroup/GetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/GetFlipH.md) method to PDF API.
- Added the [ApiGroup/GetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/GetFlipV.md) method to PDF API.
- Added the [ApiGroup/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/GetLine.md) method to PDF API.
- Added the [ApiGroup/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/GetLockAspect.md) method to PDF API.
- Added the [ApiGroup/GetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/GetLockValue.md) method to PDF API.
- Added the [ApiGroup/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/GetName.md) method to PDF API.
- Added the [ApiGroup/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/GetShadow.md) method to PDF API.
- Added the [ApiGroup/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/GetTextRange.md) method to PDF API.
- Added the [ApiGroup/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/GetTitle.md) method to PDF API.
- Added the [ApiGroup/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/HasTextContent.md) method to PDF API.
- Added the [ApiGroup/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/SetDescription.md) method to PDF API.
- Added the [ApiGroup/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/SetFill.md) method to PDF API.
- Added the [ApiGroup/SetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/SetFlipH.md) method to PDF API.
- Added the [ApiGroup/SetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/SetFlipV.md) method to PDF API.
- Added the [ApiGroup/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/SetLine.md) method to PDF API.
- Added the [ApiGroup/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/SetLockAspect.md) method to PDF API.
- Added the [ApiGroup/SetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/SetLockValue.md) method to PDF API.
- Added the [ApiGroup/SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/SetName.md) method to PDF API.
- Added the [ApiGroup/SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/SetOutLine.md) method to PDF API.
- Added the [ApiGroup/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/SetShadow.md) method to PDF API.
- Added the [ApiGroup/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/SetTitle.md) method to PDF API.
- Added the [ApiGroup/Unselect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/Unselect.md) method to PDF API.

#### ApiHideShowFormsAction class

- Added the [ApiHideShowFormsAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHideShowFormsAction.md) class to PDF API.
- Added the [ApiHideShowFormsAction/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHideShowFormsAction/Methods/GetClassType.md) method to PDF API.
- Added the [ApiHideShowFormsAction/GetNames](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHideShowFormsAction/Methods/GetNames.md) method to PDF API.
- Added the [ApiHideShowFormsAction/IsHide](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHideShowFormsAction/Methods/IsHide.md) method to PDF API.
- Added the [ApiHideShowFormsAction/SetHide](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHideShowFormsAction/Methods/SetHide.md) method to PDF API.
- Added the [ApiHideShowFormsAction/SetNames](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHideShowFormsAction/Methods/SetNames.md) method to PDF API.

#### ApiHyperlink methods

- Added the [ApiHyperlink/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHyperlink/Methods/GetTextRange.md) method to PDF API.

#### ApiImage methods

- Added the [ApiImage/Fill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/Fill.md) method to PDF API.
- Added the [ApiImage/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetDescription.md) method to PDF API.
- Added the [ApiImage/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetFill.md) method to PDF API.
- Added the [ApiImage/GetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetFlipH.md) method to PDF API.
- Added the [ApiImage/GetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetFlipV.md) method to PDF API.
- Added the [ApiImage/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetLine.md) method to PDF API.
- Added the [ApiImage/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetLockAspect.md) method to PDF API.
- Added the [ApiImage/GetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetLockValue.md) method to PDF API.
- Added the [ApiImage/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetName.md) method to PDF API.
- Added the [ApiImage/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetShadow.md) method to PDF API.
- Added the [ApiImage/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetTextRange.md) method to PDF API.
- Added the [ApiImage/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetTitle.md) method to PDF API.
- Added the [ApiImage/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/HasTextContent.md) method to PDF API.
- Added the [ApiImage/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetDescription.md) method to PDF API.
- Added the [ApiImage/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetFill.md) method to PDF API.
- Added the [ApiImage/SetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetFlipH.md) method to PDF API.
- Added the [ApiImage/SetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetFlipV.md) method to PDF API.
- Added the [ApiImage/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetLine.md) method to PDF API.
- Added the [ApiImage/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetLockAspect.md) method to PDF API.
- Added the [ApiImage/SetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetLockValue.md) method to PDF API.
- Added the [ApiImage/SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetName.md) method to PDF API.
- Added the [ApiImage/SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetOutLine.md) method to PDF API.
- Added the [ApiImage/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetShadow.md) method to PDF API.
- Added the [ApiImage/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetTitle.md) method to PDF API.
- Added the [ApiImage/Unselect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/Unselect.md) method to PDF API.

#### ApiJsAction class

- Added the [ApiJsAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiJsAction.md) class to PDF API.
- Added the [ApiJsAction/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiJsAction/Methods/GetClassType.md) method to PDF API.
- Added the [ApiJsAction/GetScript](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiJsAction/Methods/GetScript.md) method to PDF API.
- Added the [ApiJsAction/SetScript](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiJsAction/Methods/SetScript.md) method to PDF API.

#### ApiLinkAnnotation methods

- Added the [ApiLinkAnnotation/GetAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiLinkAnnotation/Methods/GetAction.md) method to PDF API.
- Added the [ApiLinkAnnotation/SetAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiLinkAnnotation/Methods/SetAction.md) method to PDF API.

#### ApiMath class

- Added the [ApiMath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiMath.md) class to PDF API.
- Added the [ApiMath/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiMath/Methods/GetClassType.md) method to PDF API.
- Added the [ApiMath/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiMath/Methods/GetText.md) method to PDF API.

#### ApiNamedAction class

- Added the [ApiNamedAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiNamedAction.md) class to PDF API.
- Added the [ApiNamedAction/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiNamedAction/Methods/GetClassType.md) method to PDF API.
- Added the [ApiNamedAction/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiNamedAction/Methods/GetName.md) method to PDF API.
- Added the [ApiNamedAction/SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiNamedAction/Methods/SetName.md) method to PDF API.

#### ApiPage methods

- Added the [ApiPage/GetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage/Methods/GetHeight.md) method to PDF API.
- Added the [ApiPage/GetSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage/Methods/GetSelection.md) method to PDF API.
- Added the [ApiPage/GetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage/Methods/GetWidth.md) method to PDF API.

#### ApiParagraph methods

- Added the [ApiParagraph/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/GetTextRange.md) method to PDF API.
- Added the [ApiParagraph/IsEmpty](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/IsEmpty.md) method to PDF API.
- Added the [ApiParagraph/SetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetLanguage.md) method to PDF API.

#### ApiResetFormsAction class

- Added the [ApiResetFormsAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiResetFormsAction.md) class to PDF API.
- Added the [ApiResetFormsAction/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiResetFormsAction/Methods/GetClassType.md) method to PDF API.
- Added the [ApiResetFormsAction/GetNames](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiResetFormsAction/Methods/GetNames.md) method to PDF API.
- Added the [ApiResetFormsAction/IsAllExcept](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiResetFormsAction/Methods/IsAllExcept.md) method to PDF API.
- Added the [ApiResetFormsAction/SetAllExcept](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiResetFormsAction/Methods/SetAllExcept.md) method to PDF API.
- Added the [ApiResetFormsAction/SetNames](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiResetFormsAction/Methods/SetNames.md) method to PDF API.

#### ApiRichContent methods

- Added the [ApiRichContent/GetElementsCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichContent/Methods/GetElementsCount.md) method to PDF API.
- Added the [ApiRichContent/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichContent/Methods/GetText.md) method to PDF API.
- Added the [ApiRichContent/RemoveAllElements](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichContent/Methods/RemoveAllElements.md) method to PDF API.
- Added the [ApiRichContent/RemoveElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichContent/Methods/RemoveElement.md) method to PDF API.

#### ApiRichParaPr methods

- Added the [ApiRichParaPr/GetJc](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParaPr/Methods/GetJc.md) method to PDF API.
- Added the [ApiRichParaPr/SetJc](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParaPr/Methods/SetJc.md) method to PDF API.

#### ApiRichParagraph methods

- Added the [ApiRichParagraph/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/Delete.md) method to PDF API.
- Added the [ApiRichParagraph/GetElementsCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetElementsCount.md) method to PDF API.
- Added the [ApiRichParagraph/GetJc](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetJc.md) method to PDF API.
- Added the [ApiRichParagraph/GetLastRunWithText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetLastRunWithText.md) method to PDF API.
- Added the [ApiRichParagraph/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetPosInParent.md) method to PDF API.
- Added the [ApiRichParagraph/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetText.md) method to PDF API.
- Added the [ApiRichParagraph/RemoveAllElements](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/RemoveAllElements.md) method to PDF API.
- Added the [ApiRichParagraph/RemoveElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/RemoveElement.md) method to PDF API.
- Added the [ApiRichParagraph/SetJc](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/SetJc.md) method to PDF API.

#### ApiRichRun methods

- Added the [ApiRichRun/AddText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/AddText.md) method to PDF API.
- Added the [ApiRichRun/ClearContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/ClearContent.md) method to PDF API.
- Added the [ApiRichRun/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/Delete.md) method to PDF API.
- Added the [ApiRichRun/GetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetBold.md) method to PDF API.
- Added the [ApiRichRun/GetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetColor.md) method to PDF API.
- Added the [ApiRichRun/GetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetFontFamily.md) method to PDF API.
- Added the [ApiRichRun/GetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetFontSize.md) method to PDF API.
- Added the [ApiRichRun/GetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetItalic.md) method to PDF API.
- Added the [ApiRichRun/GetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetStrikeout.md) method to PDF API.
- Added the [ApiRichRun/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetText.md) method to PDF API.
- Added the [ApiRichRun/GetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetUnderline.md) method to PDF API.
- Added the [ApiRichRun/GetVertAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetVertAlign.md) method to PDF API.
- Added the [ApiRichRun/RemoveAllElements](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/RemoveAllElements.md) method to PDF API.
- Added the [ApiRichRun/SetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/SetBold.md) method to PDF API.
- Added the [ApiRichRun/SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/SetColor.md) method to PDF API.
- Added the [ApiRichRun/SetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/SetFontFamily.md) method to PDF API.
- Added the [ApiRichRun/SetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/SetFontSize.md) method to PDF API.
- Added the [ApiRichRun/SetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/SetItalic.md) method to PDF API.
- Added the [ApiRichRun/SetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/SetStrikeout.md) method to PDF API.
- Added the [ApiRichRun/SetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/SetUnderline.md) method to PDF API.
- Added the [ApiRichRun/SetVertAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/SetVertAlign.md) method to PDF API.

#### ApiRichTextPr methods

- Added the [ApiRichTextPr/GetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr/Methods/GetBold.md) method to PDF API.
- Added the [ApiRichTextPr/GetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr/Methods/GetColor.md) method to PDF API.
- Added the [ApiRichTextPr/GetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr/Methods/GetFontFamily.md) method to PDF API.
- Added the [ApiRichTextPr/GetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr/Methods/GetFontSize.md) method to PDF API.
- Added the [ApiRichTextPr/GetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr/Methods/GetItalic.md) method to PDF API.
- Added the [ApiRichTextPr/GetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr/Methods/GetStrikeout.md) method to PDF API.
- Added the [ApiRichTextPr/GetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr/Methods/GetUnderline.md) method to PDF API.
- Added the [ApiRichTextPr/GetVertAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr/Methods/GetVertAlign.md) method to PDF API.
- Added the [ApiRichTextPr/SetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr/Methods/SetBold.md) method to PDF API.
- Added the [ApiRichTextPr/SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr/Methods/SetColor.md) method to PDF API.
- Added the [ApiRichTextPr/SetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr/Methods/SetFontFamily.md) method to PDF API.
- Added the [ApiRichTextPr/SetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr/Methods/SetFontSize.md) method to PDF API.
- Added the [ApiRichTextPr/SetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr/Methods/SetItalic.md) method to PDF API.
- Added the [ApiRichTextPr/SetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr/Methods/SetStrikeout.md) method to PDF API.
- Added the [ApiRichTextPr/SetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr/Methods/SetUnderline.md) method to PDF API.
- Added the [ApiRichTextPr/SetVertAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr/Methods/SetVertAlign.md) method to PDF API.

#### ApiRun methods

- Added the [ApiRun/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/GetTextRange.md) method to PDF API.
- Added the [ApiRun/SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/SetColor.md) method to PDF API.
- Added the [ApiRun/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/SetText.md) method to PDF API.

#### ApiShadow class

- Added the [ApiShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShadow.md) class to PDF API.
- Added the [ApiShadow/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShadow/Methods/GetClassType.md) method to PDF API.
- Added the [ApiShadow/GetSettings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShadow/Methods/GetSettings.md) method to PDF API.

#### ApiShape methods

- Added the [ApiShape/Fill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/Fill.md) method to PDF API.
- Added the [ApiShape/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/GetDescription.md) method to PDF API.
- Added the [ApiShape/GetDocContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/GetDocContent.md) method to PDF API.
- Added the [ApiShape/GetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/GetFlipH.md) method to PDF API.
- Added the [ApiShape/GetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/GetFlipV.md) method to PDF API.
- Added the [ApiShape/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/GetLockAspect.md) method to PDF API.
- Added the [ApiShape/GetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/GetLockValue.md) method to PDF API.
- Added the [ApiShape/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/GetName.md) method to PDF API.
- Added the [ApiShape/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/GetShadow.md) method to PDF API.
- Added the [ApiShape/GetTextFit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/GetTextFit.md) method to PDF API.
- Added the [ApiShape/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/GetTextRange.md) method to PDF API.
- Added the [ApiShape/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/GetTitle.md) method to PDF API.
- Added the [ApiShape/GetVerticalTextAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/GetVerticalTextAlign.md) method to PDF API.
- Added the [ApiShape/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/HasTextContent.md) method to PDF API.
- Added the [ApiShape/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/SetDescription.md) method to PDF API.
- Added the [ApiShape/SetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/SetFlipH.md) method to PDF API.
- Added the [ApiShape/SetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/SetFlipV.md) method to PDF API.
- Added the [ApiShape/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/SetLockAspect.md) method to PDF API.
- Added the [ApiShape/SetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/SetLockValue.md) method to PDF API.
- Added the [ApiShape/SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/SetName.md) method to PDF API.
- Added the [ApiShape/SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/SetOutLine.md) method to PDF API.
- Added the [ApiShape/SetPaddings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/SetPaddings.md) method to PDF API.
- Added the [ApiShape/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/SetShadow.md) method to PDF API.
- Added the [ApiShape/SetTextFit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/SetTextFit.md) method to PDF API.
- Added the [ApiShape/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/SetTitle.md) method to PDF API.
- Added the [ApiShape/Unselect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/Unselect.md) method to PDF API.

#### ApiShd class

- Added the [ApiShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShd.md) class to PDF API.
- Added the [ApiShd/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShd/Methods/GetClassType.md) method to PDF API.
- Added the [ApiShd/GetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShd/Methods/GetColor.md) method to PDF API.
- Added the [ApiShd/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShd/Methods/GetType.md) method to PDF API.

#### ApiSignatureField class

- Added the [ApiSignatureField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField.md) class to PDF API.
- Added the [ApiSignatureField/AddWidget](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField/Methods/AddWidget.md) method to PDF API.
- Added the [ApiSignatureField/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField/Methods/Delete.md) method to PDF API.
- Added the [ApiSignatureField/GetAllWidgets](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField/Methods/GetAllWidgets.md) method to PDF API.
- Added the [ApiSignatureField/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField/Methods/GetClassType.md) method to PDF API.
- Added the [ApiSignatureField/GetFullName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField/Methods/GetFullName.md) method to PDF API.
- Added the [ApiSignatureField/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField/Methods/GetInternalId.md) method to PDF API.
- Added the [ApiSignatureField/GetPartialName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField/Methods/GetPartialName.md) method to PDF API.
- Added the [ApiSignatureField/GetTooltip](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField/Methods/GetTooltip.md) method to PDF API.
- Added the [ApiSignatureField/GetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField/Methods/GetValue.md) method to PDF API.
- Added the [ApiSignatureField/IsReadOnly](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField/Methods/IsReadOnly.md) method to PDF API.
- Added the [ApiSignatureField/IsRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField/Methods/IsRequired.md) method to PDF API.
- Added the [ApiSignatureField/SetFullName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField/Methods/SetFullName.md) method to PDF API.
- Added the [ApiSignatureField/SetPartialName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField/Methods/SetPartialName.md) method to PDF API.
- Added the [ApiSignatureField/SetReadOnly](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField/Methods/SetReadOnly.md) method to PDF API.
- Added the [ApiSignatureField/SetRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField/Methods/SetRequired.md) method to PDF API.
- Added the [ApiSignatureField/SetTooltip](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField/Methods/SetTooltip.md) method to PDF API.
- Added the [ApiSignatureField/SetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField/Methods/SetValue.md) method to PDF API.

#### ApiSmartArt methods

- Added the [ApiSmartArt/Fill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/Fill.md) method to PDF API.
- Added the [ApiSmartArt/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/GetDescription.md) method to PDF API.
- Added the [ApiSmartArt/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/GetFill.md) method to PDF API.
- Added the [ApiSmartArt/GetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/GetFlipH.md) method to PDF API.
- Added the [ApiSmartArt/GetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/GetFlipV.md) method to PDF API.
- Added the [ApiSmartArt/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/GetLine.md) method to PDF API.
- Added the [ApiSmartArt/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/GetLockAspect.md) method to PDF API.
- Added the [ApiSmartArt/GetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/GetLockValue.md) method to PDF API.
- Added the [ApiSmartArt/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/GetName.md) method to PDF API.
- Added the [ApiSmartArt/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/GetShadow.md) method to PDF API.
- Added the [ApiSmartArt/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/GetTextRange.md) method to PDF API.
- Added the [ApiSmartArt/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/GetTitle.md) method to PDF API.
- Added the [ApiSmartArt/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/HasTextContent.md) method to PDF API.
- Added the [ApiSmartArt/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/SetDescription.md) method to PDF API.
- Added the [ApiSmartArt/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/SetFill.md) method to PDF API.
- Added the [ApiSmartArt/SetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/SetFlipH.md) method to PDF API.
- Added the [ApiSmartArt/SetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/SetFlipV.md) method to PDF API.
- Added the [ApiSmartArt/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/SetLine.md) method to PDF API.
- Added the [ApiSmartArt/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/SetLockAspect.md) method to PDF API.
- Added the [ApiSmartArt/SetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/SetLockValue.md) method to PDF API.
- Added the [ApiSmartArt/SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/SetName.md) method to PDF API.
- Added the [ApiSmartArt/SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/SetOutLine.md) method to PDF API.
- Added the [ApiSmartArt/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/SetShadow.md) method to PDF API.
- Added the [ApiSmartArt/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/SetTitle.md) method to PDF API.
- Added the [ApiSmartArt/Unselect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/Unselect.md) method to PDF API.

#### ApiStroke methods

- Added the [ApiStroke/GetBeginArrow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStroke/Methods/GetBeginArrow.md) method to PDF API.
- Added the [ApiStroke/GetCapType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStroke/Methods/GetCapType.md) method to PDF API.
- Added the [ApiStroke/GetEndArrow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStroke/Methods/GetEndArrow.md) method to PDF API.
- Added the [ApiStroke/GetJoinType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStroke/Methods/GetJoinType.md) method to PDF API.
- Added the [ApiStroke/SetBeginArrow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStroke/Methods/SetBeginArrow.md) method to PDF API.
- Added the [ApiStroke/SetCapType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStroke/Methods/SetCapType.md) method to PDF API.
- Added the [ApiStroke/SetEndArrow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStroke/Methods/SetEndArrow.md) method to PDF API.
- Added the [ApiStroke/SetJoinType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStroke/Methods/SetJoinType.md) method to PDF API.

#### ApiTable methods

- Added the [ApiTable/AddColumns](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/AddColumns.md) method to PDF API.
- Added the [ApiTable/AddElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/AddElement.md) method to PDF API.
- Added the [ApiTable/AddRows](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/AddRows.md) method to PDF API.
- Added the [ApiTable/Fill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/Fill.md) method to PDF API.
- Added the [ApiTable/GetCell](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetCell.md) method to PDF API.
- Added the [ApiTable/GetColumnWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetColumnWidth.md) method to PDF API.
- Added the [ApiTable/GetColumnsCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetColumnsCount.md) method to PDF API.
- Added the [ApiTable/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetDescription.md) method to PDF API.
- Added the [ApiTable/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetFill.md) method to PDF API.
- Added the [ApiTable/GetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetFlipH.md) method to PDF API.
- Added the [ApiTable/GetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetFlipV.md) method to PDF API.
- Added the [ApiTable/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetLine.md) method to PDF API.
- Added the [ApiTable/GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetLockAspect.md) method to PDF API.
- Added the [ApiTable/GetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetLockValue.md) method to PDF API.
- Added the [ApiTable/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetName.md) method to PDF API.
- Added the [ApiTable/GetRowsCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetRowsCount.md) method to PDF API.
- Added the [ApiTable/GetSelectedCells](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetSelectedCells.md) method to PDF API.
- Added the [ApiTable/GetSelectedColumnsCells](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetSelectedColumnsCells.md) method to PDF API.
- Added the [ApiTable/GetSelectedRows](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetSelectedRows.md) method to PDF API.
- Added the [ApiTable/GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetShadow.md) method to PDF API.
- Added the [ApiTable/GetTableDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetTableDescription.md) method to PDF API.
- Added the [ApiTable/GetTableLook](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetTableLook.md) method to PDF API.
- Added the [ApiTable/GetTableTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetTableTitle.md) method to PDF API.
- Added the [ApiTable/GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetTextRange.md) method to PDF API.
- Added the [ApiTable/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetTitle.md) method to PDF API.
- Added the [ApiTable/HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/HasTextContent.md) method to PDF API.
- Added the [ApiTable/SelectRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SelectRange.md) method to PDF API.
- Added the [ApiTable/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SetBackgroundColor.md) method to PDF API.
- Added the [ApiTable/SetColumnWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SetColumnWidth.md) method to PDF API.
- Added the [ApiTable/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SetDescription.md) method to PDF API.
- Added the [ApiTable/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SetFill.md) method to PDF API.
- Added the [ApiTable/SetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SetFlipH.md) method to PDF API.
- Added the [ApiTable/SetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SetFlipV.md) method to PDF API.
- Added the [ApiTable/SetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SetHeight.md) method to PDF API.
- Added the [ApiTable/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SetLine.md) method to PDF API.
- Added the [ApiTable/SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SetLockAspect.md) method to PDF API.
- Added the [ApiTable/SetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SetLockValue.md) method to PDF API.
- Added the [ApiTable/SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SetName.md) method to PDF API.
- Added the [ApiTable/SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SetOutLine.md) method to PDF API.
- Added the [ApiTable/SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SetShadow.md) method to PDF API.
- Added the [ApiTable/SetStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SetStyle.md) method to PDF API.
- Added the [ApiTable/SetTableDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SetTableDescription.md) method to PDF API.
- Added the [ApiTable/SetTableTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SetTableTitle.md) method to PDF API.
- Added the [ApiTable/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SetTitle.md) method to PDF API.
- Added the [ApiTable/Unselect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/Unselect.md) method to PDF API.

#### ApiTableCell methods

- Added the [ApiTableCell/AddColumns](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/AddColumns.md) method to PDF API.
- Added the [ApiTableCell/AddRows](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/AddRows.md) method to PDF API.
- Added the [ApiTableCell/Clear](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/Clear.md) method to PDF API.
- Added the [ApiTableCell/GetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/GetBackgroundColor.md) method to PDF API.
- Added the [ApiTableCell/GetIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/GetIndex.md) method to PDF API.
- Added the [ApiTableCell/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/GetInternalId.md) method to PDF API.
- Added the [ApiTableCell/GetNext](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/GetNext.md) method to PDF API.
- Added the [ApiTableCell/GetParentRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/GetParentRow.md) method to PDF API.
- Added the [ApiTableCell/GetParentTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/GetParentTable.md) method to PDF API.
- Added the [ApiTableCell/GetPrevious](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/GetPrevious.md) method to PDF API.
- Added the [ApiTableCell/GetRowIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/GetRowIndex.md) method to PDF API.
- Added the [ApiTableCell/RemoveColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/RemoveColumn.md) method to PDF API.
- Added the [ApiTableCell/RemoveRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/RemoveRow.md) method to PDF API.
- Added the [ApiTableCell/Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/Select.md) method to PDF API.
- Added the [ApiTableCell/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/SetBackgroundColor.md) method to PDF API.
- Added the [ApiTableCell/SetColumnBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/SetColumnBackgroundColor.md) method to PDF API.
- Added the [ApiTableCell/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/SetTextPr.md) method to PDF API.
- Added the [ApiTableCell/SetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/SetWidth.md) method to PDF API.

#### ApiTableRow methods

- Added the [ApiTableRow/AddRows](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow/Methods/AddRows.md) method to PDF API.
- Added the [ApiTableRow/Clear](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow/Methods/Clear.md) method to PDF API.
- Added the [ApiTableRow/GetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow/Methods/GetHeight.md) method to PDF API.
- Added the [ApiTableRow/GetIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow/Methods/GetIndex.md) method to PDF API.
- Added the [ApiTableRow/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow/Methods/GetInternalId.md) method to PDF API.
- Added the [ApiTableRow/GetNext](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow/Methods/GetNext.md) method to PDF API.
- Added the [ApiTableRow/GetParentTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow/Methods/GetParentTable.md) method to PDF API.
- Added the [ApiTableRow/GetPrevious](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow/Methods/GetPrevious.md) method to PDF API.
- Added the [ApiTableRow/MergeCells](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow/Methods/MergeCells.md) method to PDF API.
- Added the [ApiTableRow/Remove](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow/Methods/Remove.md) method to PDF API.
- Added the [ApiTableRow/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow/Methods/SetBackgroundColor.md) method to PDF API.
- Added the [ApiTableRow/SetRowPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow/Methods/SetRowPr.md) method to PDF API.
- Added the [ApiTableRow/SetTableHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow/Methods/SetTableHeader.md) method to PDF API.
- Added the [ApiTableRow/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow/Methods/SetTextPr.md) method to PDF API.

#### ApiTableRowPr class

- Added the [ApiTableRowPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRowPr.md) class to PDF API.
- Added the [ApiTableRowPr/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRowPr/Methods/GetClassType.md) method to PDF API.
- Added the [ApiTableRowPr/SetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRowPr/Methods/SetHeight.md) method to PDF API.
- Added the [ApiTableRowPr/SetTableHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRowPr/Methods/SetTableHeader.md) method to PDF API.

#### ApiTextField methods

- Added the [ApiTextField/GetFormattedValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/GetFormattedValue.md) method to PDF API.
- Added the [ApiTextField/GetPlaceholder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/GetPlaceholder.md) method to PDF API.
- Added the [ApiTextField/GetRegularExp](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/GetRegularExp.md) method to PDF API.
- Added the [ApiTextField/SetPlaceholder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetPlaceholder.md) method to PDF API.

#### ApiTextPr methods

- Added the [ApiTextPr/SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/SetColor.md) method to PDF API.
- Added the [ApiTextPr/SetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/SetLanguage.md) method to PDF API.

#### ApiTextRange class

- Added the [ApiTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange.md) class to PDF API.
- Added the [ApiTextRange/AddHyperlink](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/AddHyperlink.md) method to PDF API.
- Added the [ApiTextRange/AddText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/AddText.md) method to PDF API.
- Added the [ApiTextRange/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/Delete.md) method to PDF API.
- Added the [ApiTextRange/ExpandTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/ExpandTo.md) method to PDF API.
- Added the [ApiTextRange/Find](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/Find.md) method to PDF API.
- Added the [ApiTextRange/GetAllParagraphs](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/GetAllParagraphs.md) method to PDF API.
- Added the [ApiTextRange/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/GetClassType.md) method to PDF API.
- Added the [ApiTextRange/GetEndPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/GetEndPos.md) method to PDF API.
- Added the [ApiTextRange/GetParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/GetParagraph.md) method to PDF API.
- Added the [ApiTextRange/GetRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/GetRange.md) method to PDF API.
- Added the [ApiTextRange/GetStartPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/GetStartPos.md) method to PDF API.
- Added the [ApiTextRange/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/GetText.md) method to PDF API.
- Added the [ApiTextRange/GetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/GetTextPr.md) method to PDF API.
- Added the [ApiTextRange/IntersectWith](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/IntersectWith.md) method to PDF API.
- Added the [ApiTextRange/MoveCursorToPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/MoveCursorToPos.md) method to PDF API.
- Added the [ApiTextRange/Replace](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/Replace.md) method to PDF API.
- Added the [ApiTextRange/Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/Select.md) method to PDF API.
- Added the [ApiTextRange/SetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/SetBold.md) method to PDF API.
- Added the [ApiTextRange/SetCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/SetCaps.md) method to PDF API.
- Added the [ApiTextRange/SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/SetColor.md) method to PDF API.
- Added the [ApiTextRange/SetDoubleStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/SetDoubleStrikeout.md) method to PDF API.
- Added the [ApiTextRange/SetEndPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/SetEndPos.md) method to PDF API.
- Added the [ApiTextRange/SetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/SetFontFamily.md) method to PDF API.
- Added the [ApiTextRange/SetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/SetFontSize.md) method to PDF API.
- Added the [ApiTextRange/SetHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/SetHighlight.md) method to PDF API.
- Added the [ApiTextRange/SetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/SetItalic.md) method to PDF API.
- Added the [ApiTextRange/SetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/SetLanguage.md) method to PDF API.
- Added the [ApiTextRange/SetSmallCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/SetSmallCaps.md) method to PDF API.
- Added the [ApiTextRange/SetSpacing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/SetSpacing.md) method to PDF API.
- Added the [ApiTextRange/SetStartPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/SetStartPos.md) method to PDF API.
- Added the [ApiTextRange/SetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/SetStrikeout.md) method to PDF API.
- Added the [ApiTextRange/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/SetText.md) method to PDF API.
- Added the [ApiTextRange/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/SetTextPr.md) method to PDF API.
- Added the [ApiTextRange/SetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/SetUnderline.md) method to PDF API.
- Added the [ApiTextRange/SetVertAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/SetVertAlign.md) method to PDF API.
- Added the [ApiTextRange/ToHtml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange/Methods/ToHtml.md) method to PDF API.

#### ApiUriAction class

- Added the [ApiUriAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiUriAction.md) class to PDF API.
- Added the [ApiUriAction/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiUriAction/Methods/GetClassType.md) method to PDF API.
- Added the [ApiUriAction/GetUri](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiUriAction/Methods/GetUri.md) method to PDF API.
- Added the [ApiUriAction/SetUri](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiUriAction/Methods/SetUri.md) method to PDF API.

#### PdfFile class

- Added the [PdfFile](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/PdfFile.md) class to PDF API.
- Added the [PdfFile/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/PdfFile/Methods/GetClassType.md) method to PDF API.
- Added the [PdfFile/ToBase64](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/PdfFile/Methods/ToBase64.md) method to PDF API.

#### PDF types

- Added the [ChartTypeLegacy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ChartTypeLegacy.md) type to the simple type definitions.
- Added the [DocQuads](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/DocQuads.md) type to the simple type definitions.
- Added the [DocSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/DocSelection.md) type to the simple type definitions.
- Added the [DrawingLockType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/DrawingLockType.md) type to the simple type definitions.
- Added the [GoToType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/GoToType.md) type to the simple type definitions.
- Added the [HorTextAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/HorTextAlign.md) type to the simple type definitions.
- Added the [LineCapType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/LineCapType.md) type to the simple type definitions.
- Added the [LineEndSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/LineEndSize.md) type to the simple type definitions.
- Added the [LineEndType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/LineEndType.md) type to the simple type definitions.
- Added the [LineJoinType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/LineJoinType.md) type to the simple type definitions.
- Added the [NamedActionType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/NamedActionType.md) type to the simple type definitions.
- Added the [PagePoint](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/PagePoint.md) type to the simple type definitions.
- Added the [PageSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/PageSelection.md) type to the simple type definitions.
- Added the [SearchMatch](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/SearchMatch.md) type to the simple type definitions.
- Added the [SearchResults](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/SearchResults.md) type to the simple type definitions.
- Added the [ShadowSettings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ShadowSettings.md) type to the simple type definitions.
- Added the [ShapesMergeOperation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ShapesMergeOperation.md) type to the simple type definitions.
- Added the [TableLook](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/TableLook.md) type to the simple type definitions.
- Added the [TableWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/TableWidth.md) type to the simple type definitions.
- Added the [TextFitType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/TextFitType.md) type to the simple type definitions.
- Added the [TextVertAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/TextVertAlign.md) type to the simple type definitions.
- Added the [ToHtmlOptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ToHtmlOptions.md) type to the simple type definitions.
- Added the [WidgetTextAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/WidgetTextAlign.md) type to the simple type definitions.

## Version 9.4.1

### Document methods

- Added the [Api/CompareDocuments](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CompareDocuments.md) method to Document API.

## Version 9.4

### Breaking changes

- Updated the [Api/CreateTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateTable.md) method in Document API - changed the parameter order from `Api.CreateTable(cols, rows)` to `Api.CreateTable(rows, cols)`.
- Updated the [Api/CreateTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateTable.md) method in Presentation API - changed the parameter order from `Api.CreateTable(cols, rows)` to `Api.CreateTable(rows, cols)`.

### Document methods

- Added the [Api/MergeDocuments](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/MergeDocuments.md) method to Document API.

### Color methods

- Added the [Api/Color](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/Color.md) method to Document API.
- Added the [Api/Color](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/Color.md) method to Spreadsheet API.
- Added the [Api/Color](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/Color.md) method to Presentation API.
- Added the [Api/Color](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/Color.md) method to PDF API.

### Signature form

- Added the [ApiSignatureForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm.md) class to Document API.
- Added the [ApiSignatureForm/GetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/GetValue.md) method to Document API.
- Added the [ApiSignatureForm/SetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSignatureForm/Methods/SetValue.md) method to Document API.

- Added the [ApiSignatureForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiSignatureForm.md) class to Form API.
- Added the [Api/CreateSignatureForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Api/Methods/CreateSignatureForm.md) method to Form API.
- Added the [ApiSignatureForm/GetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiSignatureForm/Methods/GetValue.md) method to Form API.
- Added the [ApiSignatureForm/SetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiSignatureForm/Methods/SetValue.md) method to Form API.

### Form methods

- Added the [ApiFormBase/IsFilled](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/IsFilled.md) method to Document API.
- Added the [ApiFormBase/IsFilled](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormBase/Methods/IsFilled.md) method to Form API.

### Highlight methods

- Added the [ApiDocument/GetFormsHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetFormsHighlight.md) method to Document API.
- Added the [ApiDocument/GetControlsHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetControlsHighlight.md) method to Document API.
- Added the [ApiDocument/GetFormsHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDocument/Methods/GetFormsHighlight.md) method to Form API.

### List object methods

- Added the [ApiWorksheet/AddListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/AddListObject.md) method to Spreadsheet API.
- Added the [ApiWorksheet/GetListObjects](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/GetListObjects.md) method to Spreadsheet API.

- Added the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) class to Spreadsheet API.
- Added the [ApiListObject/GetActive](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetActive.md) method to Spreadsheet API.
- Added the [ApiListObject/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetName.md) method to Spreadsheet API.
- Added the [ApiListObject/SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetName.md) method to Spreadsheet API.
- Added the [ApiListObject/GetDisplayName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetDisplayName.md) method to Spreadsheet API.
- Added the [ApiListObject/SetDisplayName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetDisplayName.md) method to Spreadsheet API.
- Added the [ApiListObject/GetAlternativeText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetAlternativeText.md) method to Spreadsheet API.
- Added the [ApiListObject/SetAlternativeText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetAlternativeText.md) method to Spreadsheet API.
- Added the [ApiListObject/GetComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetComment.md) method to Spreadsheet API.
- Added the [ApiListObject/SetComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetComment.md) method to Spreadsheet API.
- Added the [ApiListObject/GetSummary](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetSummary.md) method to Spreadsheet API.
- Added the [ApiListObject/SetSummary](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetSummary.md) method to Spreadsheet API.
- Added the [ApiListObject/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetParent.md) method to Spreadsheet API.
- Added the [ApiListObject/GetRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetRange.md) method to Spreadsheet API.
- Added the [ApiListObject/GetHeaderRowRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetHeaderRowRange.md) method to Spreadsheet API.
- Added the [ApiListObject/GetDataBodyRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetDataBodyRange.md) method to Spreadsheet API.
- Added the [ApiListObject/GetTotalsRowRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetTotalsRowRange.md) method to Spreadsheet API.
- Added the [ApiListObject/GetSourceType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetSourceType.md) method to Spreadsheet API.
- Added the [ApiListObject/GetTableStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetTableStyle.md) method to Spreadsheet API.
- Added the [ApiListObject/SetTableStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetTableStyle.md) method to Spreadsheet API.
- Added the [ApiListObject/GetShowHeaders](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetShowHeaders.md) method to Spreadsheet API.
- Added the [ApiListObject/SetShowHeaders](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetShowHeaders.md) method to Spreadsheet API.
- Added the [ApiListObject/GetShowTotals](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetShowTotals.md) method to Spreadsheet API.
- Added the [ApiListObject/SetShowTotals](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetShowTotals.md) method to Spreadsheet API.
- Added the [ApiListObject/GetShowAutoFilter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetShowAutoFilter.md) method to Spreadsheet API.
- Added the [ApiListObject/SetShowAutoFilter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetShowAutoFilter.md) method to Spreadsheet API.
- Added the [ApiListObject/GetShowAutoFilterDropDown](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetShowAutoFilterDropDown.md) method to Spreadsheet API.
- Added the [ApiListObject/SetShowAutoFilterDropDown](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetShowAutoFilterDropDown.md) method to Spreadsheet API.
- Added the [ApiListObject/GetShowTableStyleColumnStripes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetShowTableStyleColumnStripes.md) method to Spreadsheet API.
- Added the [ApiListObject/SetShowTableStyleColumnStripes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetShowTableStyleColumnStripes.md) method to Spreadsheet API.
- Added the [ApiListObject/GetShowTableStyleFirstColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetShowTableStyleFirstColumn.md) method to Spreadsheet API.
- Added the [ApiListObject/SetShowTableStyleFirstColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetShowTableStyleFirstColumn.md) method to Spreadsheet API.
- Added the [ApiListObject/GetShowTableStyleLastColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetShowTableStyleLastColumn.md) method to Spreadsheet API.
- Added the [ApiListObject/SetShowTableStyleLastColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetShowTableStyleLastColumn.md) method to Spreadsheet API.
- Added the [ApiListObject/GetShowTableStyleRowStripes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetShowTableStyleRowStripes.md) method to Spreadsheet API.
- Added the [ApiListObject/SetShowTableStyleRowStripes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetShowTableStyleRowStripes.md) method to Spreadsheet API.
- Added the [ApiListObject/GetAutoFilter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetAutoFilter.md) method to Spreadsheet API.
- Added the [ApiListObject/GetListColumns](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetListColumns.md) method to Spreadsheet API.
- Added the [ApiListObject/AddListColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/AddListColumn.md) method to Spreadsheet API.
- Added the [ApiListObject/GetListRows](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetListRows.md) method to Spreadsheet API.
- Added the [ApiListObject/AddListRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/AddListRow.md) method to Spreadsheet API.
- Added the [ApiListObject/GetSort](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetSort.md) method to Spreadsheet API.
- Added the [ApiListObject/Resize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/Resize.md) method to Spreadsheet API.
- Added the [ApiListObject/Unlist](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/Unlist.md) method to Spreadsheet API.
- Added the [ApiListObject/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/Delete.md) method to Spreadsheet API.
- Added the `Active` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `Name` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `DisplayName` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `AlternativeText` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `Comment` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `Summary` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `Parent` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `Range` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `HeaderRowRange` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `DataBodyRange` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `TotalsRowRange` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `SourceType` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `TableStyle` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `ShowHeaders` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `ShowTotals` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `ShowAutoFilter` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `ShowAutoFilterDropDown` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `ShowTableStyleColumnStripes` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `ShowTableStyleFirstColumn` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `ShowTableStyleLastColumn` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `ShowTableStyleRowStripes` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `AutoFilter` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.
- Added the `Sort` property to the [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) object of Spreadsheet API.

- Added the [ApiListColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn.md) class to Spreadsheet API.
- Added the [ApiListColumn/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/GetName.md) method to Spreadsheet API.
- Added the [ApiListColumn/SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/SetName.md) method to Spreadsheet API.
- Added the [ApiListColumn/GetIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/GetIndex.md) method to Spreadsheet API.
- Added the [ApiListColumn/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/GetParent.md) method to Spreadsheet API.
- Added the [ApiListColumn/GetRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/GetRange.md) method to Spreadsheet API.
- Added the [ApiListColumn/GetDataBodyRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/GetDataBodyRange.md) method to Spreadsheet API.
- Added the [ApiListColumn/GetTotalsCalculation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/GetTotalsCalculation.md) method to Spreadsheet API.
- Added the [ApiListColumn/SetTotalsCalculation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/SetTotalsCalculation.md) method to Spreadsheet API.
- Added the [ApiListColumn/GetTotal](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/GetTotal.md) method to Spreadsheet API.
- Added the [ApiListColumn/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/Delete.md) method to Spreadsheet API.
- Added the `Name` property to the [ApiListColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn.md) object of Spreadsheet API.
- Added the `Index` property to the [ApiListColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn.md) object of Spreadsheet API.
- Added the `Parent` property to the [ApiListColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn.md) object of Spreadsheet API.
- Added the `Range` property to the [ApiListColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn.md) object of Spreadsheet API.
- Added the `DataBodyRange` property to the [ApiListColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn.md) object of Spreadsheet API.
- Added the `TotalsCalculation` property to the [ApiListColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn.md) object of Spreadsheet API.
- Added the `Total` property to the [ApiListColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn.md) object of Spreadsheet API.

- Added the [ApiListRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListRow.md) class to Spreadsheet API.
- Added the [ApiListRow/GetIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListRow/Methods/GetIndex.md) method to Spreadsheet API.
- Added the [ApiListRow/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListRow/Methods/GetParent.md) method to Spreadsheet API.
- Added the [ApiListRow/GetRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListRow/Methods/GetRange.md) method to Spreadsheet API.
- Added the [ApiListRow/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListRow/Methods/Delete.md) method to Spreadsheet API.
- Added the `Index` property to the [ApiListRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListRow.md) object of Spreadsheet API.
- Added the `Parent` property to the [ApiListRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListRow.md) object of Spreadsheet API.
- Added the `Range` property to the [ApiListRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListRow.md) object of Spreadsheet API.

- Added the [ApiSort](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort.md) class to Spreadsheet API.
- Added the [ApiSort/GetSortFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/GetSortFields.md) method to Spreadsheet API.
- Added the [ApiSort/GetMatchCase](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/GetMatchCase.md) method to Spreadsheet API.
- Added the [ApiSort/SetMatchCase](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/SetMatchCase.md) method to Spreadsheet API.
- Added the [ApiSort/GetHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/GetHeader.md) method to Spreadsheet API.
- Added the [ApiSort/GetOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/GetOrientation.md) method to Spreadsheet API.
- Added the [ApiSort/SetOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/SetOrientation.md) method to Spreadsheet API.
- Added the [ApiSort/GetSortMethod](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/GetSortMethod.md) method to Spreadsheet API.
- Added the [ApiSort/SetSortMethod](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/SetSortMethod.md) method to Spreadsheet API.
- Added the [ApiSort/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/GetParent.md) method to Spreadsheet API.
- Added the [ApiSort/GetRng](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/GetRng.md) method to Spreadsheet API.
- Added the [ApiSort/Apply](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/Apply.md) method to Spreadsheet API.
- Added the `SortFields` property to the [ApiSort](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort.md) object of Spreadsheet API.
- Added the `MatchCase` property to the [ApiSort](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort.md) object of Spreadsheet API.
- Added the `Header` property to the [ApiSort](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort.md) object of Spreadsheet API.
- Added the `Orientation` property to the [ApiSort](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort.md) object of Spreadsheet API.
- Added the `SortMethod` property to the [ApiSort](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort.md) object of Spreadsheet API.
- Added the `Parent` property to the [ApiSort](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort.md) object of Spreadsheet API.
- Added the `Rng` property to the [ApiSort](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort.md) object of Spreadsheet API.

- Added the [ApiSortFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortFields.md) class to Spreadsheet API.
- Added the [ApiSortFields/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortFields/Methods/GetParent.md) method to Spreadsheet API.
- Added the [ApiSortFields/GetCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortFields/Methods/GetCount.md) method to Spreadsheet API.
- Added the [ApiSortFields/Item](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortFields/Methods/Item.md) method to Spreadsheet API.
- Added the [ApiSortFields/Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortFields/Methods/Add.md) method to Spreadsheet API.
- Added the [ApiSortFields/Add2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortFields/Methods/Add2.md) method to Spreadsheet API.
- Added the [ApiSortFields/Clear](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortFields/Methods/Clear.md) method to Spreadsheet API.
- Added the `Parent` property to the [ApiSortFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortFields.md) object of Spreadsheet API.
- Added the `Count` property to the [ApiSortFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortFields.md) object of Spreadsheet API.

- Added the [ApiSortField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField.md) class to Spreadsheet API.
- Added the [ApiSortField/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/GetParent.md) method to Spreadsheet API.
- Added the [ApiSortField/GetKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/GetKey.md) method to Spreadsheet API.
- Added the [ApiSortField/GetSortOn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/GetSortOn.md) method to Spreadsheet API.
- Added the [ApiSortField/SetSortOn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/SetSortOn.md) method to Spreadsheet API.
- Added the [ApiSortField/GetOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/GetOrder.md) method to Spreadsheet API.
- Added the [ApiSortField/SetOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/SetOrder.md) method to Spreadsheet API.
- Added the [ApiSortField/GetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/GetPriority.md) method to Spreadsheet API.
- Added the [ApiSortField/SetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/SetPriority.md) method to Spreadsheet API.
- Added the [ApiSortField/GetSortOnValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/GetSortOnValue.md) method to Spreadsheet API.
- Added the [ApiSortField/SetSortOnColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/SetSortOnColor.md) method to Spreadsheet API.
- Added the [ApiSortField/ModifyKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/ModifyKey.md) method to Spreadsheet API.
- Added the [ApiSortField/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/Delete.md) method to Spreadsheet API.
- Added the `Parent` property to the [ApiSortField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField.md) object of Spreadsheet API.
- Added the `Key` property to the [ApiSortField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField.md) object of Spreadsheet API.
- Added the `SortOn` property to the [ApiSortField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField.md) object of Spreadsheet API.
- Added the `Order` property to the [ApiSortField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField.md) object of Spreadsheet API.
- Added the `Priority` property to the [ApiSortField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField.md) object of Spreadsheet API.
- Added the `SortOnValue` property to the [ApiSortField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField.md) object of Spreadsheet API.

### Spreadsheet methods

- Added the [Api/GetDefNames](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/GetDefNames.md) method to Spreadsheet API.
- Added the [ApiRange/FillDown](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/FillDown.md) method to Spreadsheet API.
- Added the [ApiRange/FillUp](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/FillUp.md) method to Spreadsheet API.
- Added the [ApiRange/FillRight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/FillRight.md) method to Spreadsheet API.
- Added the [ApiRange/FillLeft](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/FillLeft.md) method to Spreadsheet API.
- Added the [ApiRange/SetFormula](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/SetFormula.md) method to Spreadsheet API.

### Text form methods

- Added the [ApiTextForm/GetFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetFormat.md) method to Document API.
- Added the [ApiTextForm/SetFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetFormat.md) method to Document API.
- Added the [ApiTextForm/GetAllowedSymbols](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetAllowedSymbols.md) method to Document API.
- Added the [ApiTextForm/SetAllowedSymbols](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetAllowedSymbols.md) method to Document API.

- Added the [ApiTextForm/GetFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiTextForm/Methods/GetFormat.md) method to Form API.
- Added the [ApiTextForm/SetFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiTextForm/Methods/SetFormat.md) method to Form API.
- Added the [ApiTextForm/GetAllowedSymbols](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiTextForm/Methods/GetAllowedSymbols.md) method to Form API.
- Added the [ApiTextForm/SetAllowedSymbols](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiTextForm/Methods/SetAllowedSymbols.md) method to Form API.

### Paragraph properties methods

- Added the [ApiParaPr/GetTopBorder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/GetTopBorder.md) method to Document API.
- Added the [ApiParaPr/GetLeftBorder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/GetLeftBorder.md) method to Document API.
- Added the [ApiParaPr/GetRightBorder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/GetRightBorder.md) method to Document API.
- Added the [ApiParaPr/GetBottomBorder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/GetBottomBorder.md) method to Document API.
- Added the [ApiParaPr/GetBetweenBorder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/GetBetweenBorder.md) method to Document API.
- Added the [ApiParaPr/GetKeepLines](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/GetKeepLines.md) method to Document API.
- Added the [ApiParaPr/GetKeepNext](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/GetKeepNext.md) method to Document API.
- Added the [ApiParaPr/GetNumPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/GetNumPr.md) method to Document API.
- Added the [ApiParaPr/GetPageBreakBefore](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/GetPageBreakBefore.md) method to Document API.
- Added the [ApiParaPr/GetTabs](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/GetTabs.md) method to Document API.
- Added the [ApiParaPr/GetWidowControl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/GetWidowControl.md) method to Document API.
- Added the [ApiParaPr/GetContextualSpacing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/GetContextualSpacing.md) method to Document API.

### Content control methods

- Added the [ApiInlineLvlSdt/SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/SetColor.md) method to Document API.
- Added the [ApiInlineLvlSdt/GetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/GetColor.md) method to Document API.

## Version 9.3

### Autofilter methods

- Added the [ApiWorksheet/GetAutoFilter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/GetAutoFilter.md) method to Spreadsheet API.
- Added the [ApiAutoFilter/ApplyFilter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAutoFilter/Methods/ApplyFilter.md) method to Spreadsheet API.
- Added the [ApiAutoFilter/GetFilterMode](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAutoFilter/Methods/GetFilterMode.md) method to Spreadsheet API.
- Added the [ApiAutoFilter/GetFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAutoFilter/Methods/GetFilters.md) method to Spreadsheet API.
- Added the [ApiAutoFilter/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAutoFilter/Methods/GetParent.md) method to Spreadsheet API.
- Added the [ApiAutoFilter/GetRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAutoFilter/Methods/GetRange.md) method to Spreadsheet API.
- Added the [ApiAutoFilter/ShowAllData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAutoFilter/Methods/ShowAllData.md) method to Spreadsheet API.

### Filter methods

- Added the [ApiFilter/GetCriteria1](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFilter/Methods/GetCriteria1.md) method to Spreadsheet API.
- Added the [ApiFilter/GetCriteria2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFilter/Methods/GetCriteria2.md) method to Spreadsheet API.
- Added the [ApiFilter/GetOn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFilter/Methods/GetOn.md) method to Spreadsheet API.
- Added the [ApiFilter/GetOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFilter/Methods/GetOperator.md) method to Spreadsheet API.
- Added the [ApiFilter/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFilter/Methods/GetParent.md) method to Spreadsheet API.

### Validation methods

- Added the [ApiRange/GetValidation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/GetValidation.md) method to Spreadsheet API.
- Added the [ApiValidation/Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/Add.md) method to Spreadsheet API.
- Added the [ApiValidation/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/Delete.md) method to Spreadsheet API.
- Added the [ApiValidation/Modify](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/Modify.md) method to Spreadsheet API.
- Added the [ApiValidation/GetAlertStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetAlertStyle.md) method to Spreadsheet API.
- Added the [ApiValidation/GetErrorMessage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetErrorMessage.md) method to Spreadsheet API.
- Added the [ApiValidation/GetErrorTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetErrorTitle.md) method to Spreadsheet API.
- Added the [ApiValidation/GetFormula1](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetFormula1.md) method to Spreadsheet API.
- Added the [ApiValidation/GetFormula2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetFormula2.md) method to Spreadsheet API.
- Added the [ApiValidation/GetIgnoreBlank](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetIgnoreBlank.md) method to Spreadsheet API.
- Added the [ApiValidation/GetInCellDropdown](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetInCellDropdown.md) method to Spreadsheet API.
- Added the [ApiValidation/GetInputMessage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetInputMessage.md) method to Spreadsheet API.
- Added the [ApiValidation/GetInputTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetInputTitle.md) method to Spreadsheet API.
- Added the [ApiValidation/GetOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetOperator.md) method to Spreadsheet API.
- Added the [ApiValidation/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetParent.md) method to Spreadsheet API.
- Added the [ApiValidation/GetShowError](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetShowError.md) method to Spreadsheet API.
- Added the [ApiValidation/GetShowInput](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetShowInput.md) method to Spreadsheet API.
- Added the [ApiValidation/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetType.md) method to Spreadsheet API.
- Added the [ApiValidation/SetErrorMessage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/SetErrorMessage.md) method to Spreadsheet API.
- Added the [ApiValidation/SetErrorTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/SetErrorTitle.md) method to Spreadsheet API.
- Added the [ApiValidation/SetIgnoreBlank](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/SetIgnoreBlank.md) method to Spreadsheet API.
- Added the [ApiValidation/SetInCellDropdown](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/SetInCellDropdown.md) method to Spreadsheet API.
- Added the [ApiValidation/SetInputMessage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/SetInputMessage.md) method to Spreadsheet API.
- Added the [ApiValidation/SetInputTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/SetInputTitle.md) method to Spreadsheet API.
- Added the [ApiValidation/SetShowError](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/SetShowError.md) method to Spreadsheet API.
- Added the [ApiValidation/SetShowInput](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/SetShowInput.md) method to Spreadsheet API.

### Color methods

- Added the [Api/AutoColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/AutoColor.md) method to Document API.
- Added the [Api/RGB](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/RGB.md) method to Document API.
- Added the [Api/RGBA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/RGBA.md) method to Document API.
- Added the [Api/HexColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/HexColor.md) method to Document API.
- Added the [Api/ThemeColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/ThemeColor.md) method to Document API.

- Added the [ApiColor/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor/Methods/GetClassType.md) method to Document API.
- Added the [ApiColor/IsAutoColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor/Methods/IsAutoColor.md) method to Document API.
- Added the [ApiColor/IsThemeColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor/Methods/IsThemeColor.md) method to Document API.
- Added the [ApiColor/GetRGB](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor/Methods/GetRGB.md) method to Document API.
- Added the [ApiColor/GetRGBA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor/Methods/GetRGBA.md) method to Document API.
- Added the [ApiColor/GetHex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor/Methods/GetHex.md) method to Document API.

- Updated the [ApiRange/SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/SetColor.md) method in Document API to accept `ApiColor` instances.
- Updated the [ApiRange/SetShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/SetShd.md) method in Document API to accept `ApiColor` instances.
- Updated the [ApiDocument/SetFormsHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/SetFormsHighlight.md) method in Document API to accept `ApiColor` instances.
- Updated the [ApiDocument/SetControlsHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/SetControlsHighlight.md) method in Document API to accept `ApiColor` instances.
- Updated the [ApiParagraph/SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/SetColor.md) method in Document API to accept `ApiColor` instances.
- Updated the [ApiRun/SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun/Methods/SetColor.md) method in Document API to accept `ApiColor` instances.
- Updated the [ApiRun/SetShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun/Methods/SetShd.md) method in Document API to accept `ApiColor` instances.
- Updated the [ApiTable/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/SetBackgroundColor.md) method in Document API to accept `ApiColor` instances.
- Updated the [ApiTableRow/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableRow/Methods/SetBackgroundColor.md) method in Document API to accept `ApiColor` instances.
- Updated the [ApiTableCell/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableCell/Methods/SetBackgroundColor.md) method in Document API to accept `ApiColor` instances.
- Added the [ApiTableCell/GetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableCell/Methods/GetBackgroundColor.md) method to Document API.
- Updated the [ApiTableCell/SetColumnBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableCell/Methods/SetColumnBackgroundColor.md) method in Document API to accept `ApiColor` instances.
- Updated the [ApiTextPr/SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/SetColor.md) method in Document API to accept `ApiColor` instances.
- Updated the [ApiTextPr/GetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetColor.md) method in Document API.
- Updated the [ApiTextPr/SetShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/SetShd.md) method in Document API to accept `ApiColor` instances.
- Updated the [ApiTextPr/GetShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetShd.md) method in Document API.
- Updated the [ApiParaPr/SetShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/SetShd.md) method in Document API to accept `ApiColor` instances.
- Updated the [ApiParaPr/GetShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/GetShd.md) method in Document API.
- Updated the [ApiInlineLvlSdt/SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/SetBorderColor.md) method in Document API to accept `ApiColor` instances.
- Updated the [ApiInlineLvlSdt/GetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/GetBorderColor.md) method in Document API.
- Updated the [ApiInlineLvlSdt/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/SetBackgroundColor.md) method in Document API to accept `ApiColor` instances.
- Updated the [ApiInlineLvlSdt/GetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/GetBackgroundColor.md) method in Document API.
- Updated the [ApiFormBase/SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetBorderColor.md) method in Document API to accept `ApiColor` instances.
- Added the [ApiFormBase/GetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetBorderColor.md) method to Document API.
- Updated the [ApiFormBase/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetBackgroundColor.md) method in Document API to accept `ApiColor` instances.
- Added the [ApiFormBase/GetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetBackgroundColor.md) method to Document API.
- Updated the [Api/CreateSolidFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateSolidFill.md) method in Document API to accept `ApiColor` instances.
- Updated the [Api/CreatePatternFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreatePatternFill.md) method in Document API to accept `ApiColor` instances.
- Updated the [Api/CreateGradientStop](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateGradientStop.md) method in Document API to accept `ApiColor` instances.
- Updated the [Api/CreateThemeColorScheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateThemeColorScheme.md) method in Presentation API.

### Footnote/endnote methods

- Added the [ApiDocument/GetCurrentFootEndnote](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetCurrentFootEndnote.md) method to Document API.
- Added the [ApiDocumentContent/IsFootnote](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/IsFootnote.md) method to Document API.
- Added the [ApiDocumentContent/IsEndnote](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/IsEndnote.md) method to Document API.
- Added the [ApiDocumentContent/SelectNoteReference](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/SelectNoteReference.md) method to Document API.

### Transition methods

- Added the [Api/CreateSlideShowTransition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateSlideShowTransition.md) method to the Presentation API.
- Added the [ApiSlide/GetSlideShowTransition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/GetSlideShowTransition.md) method to the Presentation API.
- Added the [ApiSlide/SetSlideShowTransition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/SetSlideShowTransition.md) method to the Presentation API.

- Added the [ApiSlideShowTransition/GetEntryEffect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlideShowTransition/Methods/GetEntryEffect.md) method to the Presentation API.
- Added the [ApiSlideShowTransition/SetEntryEffect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlideShowTransition/Methods/SetEntryEffect.md) method to the Presentation API.
- Added the [ApiSlideShowTransition/GetDuration](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlideShowTransition/Methods/GetDuration.md) method to the Presentation API.
- Added the [ApiSlideShowTransition/SetDuration](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlideShowTransition/Methods/SetDuration.md) method to the Presentation API.
- Added the [ApiSlideShowTransition/GetSpeed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlideShowTransition/Methods/GetSpeed.md) method to the Presentation API.
- Added the [ApiSlideShowTransition/SetSpeed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlideShowTransition/Methods/SetSpeed.md) method to the Presentation API.
- Added the [ApiSlideShowTransition/GetAdvanceOnClick](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlideShowTransition/Methods/GetAdvanceOnClick.md) method to the Presentation API.
- Added the [ApiSlideShowTransition/SetAdvanceOnClick](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlideShowTransition/Methods/SetAdvanceOnClick.md) method to the Presentation API.
- Added the [ApiSlideShowTransition/GetAdvanceOnTime](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlideShowTransition/Methods/GetAdvanceOnTime.md) method to the Presentation API.
- Added the [ApiSlideShowTransition/SetAdvanceOnTime](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlideShowTransition/Methods/SetAdvanceOnTime.md) method to the Presentation API.
- Added the [ApiSlideShowTransition/GetAdvanceTime](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlideShowTransition/Methods/GetAdvanceTime.md) method to the Presentation API.
- Added the [ApiSlideShowTransition/SetAdvanceTime](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlideShowTransition/Methods/SetAdvanceTime.md) method to the Presentation API.

### Hyperlink methods

- Added the [Api/CreateHyperlink](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateHyperlink.md) method to the Presentation API.
- Added the [ApiDrawing/SetHyperlink](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/SetHyperlink.md) method to the Presentation API.

### Fill and Stroke methods

- Added the [ApiShape/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape/Methods/SetFill.md) method to the Document API.
- Added the [ApiShape/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape/Methods/GetFill.md) method to the Document API.
- Added the [ApiShape/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape/Methods/SetLine.md) method to the Document API.
- Added the [ApiShape/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape/Methods/GetLine.md) method to the Document API.
- Added the [ApiFill/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFill/Methods/GetType.md) method to the Document API.
- Added the [ApiStroke/GetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiStroke/Methods/GetWidth.md) method to the Document API.
- Added the [ApiStroke/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiStroke/Methods/GetFill.md) method to the Document API.
- Added the [ApiStroke/GetDashType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiStroke/Methods/GetDashType.md) method to the Document API.

- Added the [ApiShape/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/SetFill.md) method to the Spreadsheet API.
- Added the [ApiShape/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/GetFill.md) method to the Spreadsheet API.
- Added the [ApiShape/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/SetLine.md) method to the Spreadsheet API.
- Added the [ApiShape/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/GetLine.md) method to the Spreadsheet API.
- Added the [ApiFill/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFill/Methods/GetType.md) method to the Spreadsheet API.
- Added the [ApiStroke/GetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiStroke/Methods/GetWidth.md) method to the Spreadsheet API.
- Added the [ApiStroke/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiStroke/Methods/GetFill.md) method to the Spreadsheet API.
- Added the [ApiStroke/GetDashType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiStroke/Methods/GetDashType.md) method to the Spreadsheet API.

- Added the [ApiShape/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/SetFill.md) method to the Presentation API.
- Added the [ApiShape/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/GetFill.md) method to the Presentation API.
- Added the [ApiShape/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/SetLine.md) method to the Presentation API.
- Added the [ApiShape/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/GetLine.md) method to the Presentation API.
- Added the [ApiFill/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiFill/Methods/GetType.md) method to the Presentation API.
- Added the [ApiStroke/GetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiStroke/Methods/GetWidth.md) method to the Presentation API.
- Added the [ApiStroke/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiStroke/Methods/GetFill.md) method to the Presentation API.
- Added the [ApiStroke/GetDashType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiStroke/Methods/GetDashType.md) method to the Presentation API.

### Animation methods

- Added the [ApiSlide/GetTimeLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/GetTimeLine.md) method to the Presentation API.

- Added the [ApiTimeLine/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTimeLine/Methods/GetClassType.md) method to the Presentation API.
- Added the [ApiTimeLine/GetMainSequence](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTimeLine/Methods/GetMainSequence.md) method to the Presentation API.
- Added the [ApiTimeLine/GetInteractiveSequences](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTimeLine/Methods/GetInteractiveSequences.md) method to the Presentation API.

- Added the [ApiAnimationSequence/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiAnimationSequence/Methods/GetClassType.md) method to the Presentation API.
- Added the [ApiAnimationSequence/GetCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiAnimationSequence/Methods/GetCount.md) method to the Presentation API.
- Added the [ApiAnimationSequence/GetEffect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiAnimationSequence/Methods/GetEffect.md) method to the Presentation API.
- Added the [ApiAnimationSequence/AddEffect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiAnimationSequence/Methods/AddEffect.md) method to the Presentation API.
- Added the [ApiAnimationSequence/RemoveAllEffects](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiAnimationSequence/Methods/RemoveAllEffects.md) method to the Presentation API.

- Added the [ApiAnimationEffect/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiAnimationEffect/Methods/GetClassType.md) method to the Presentation API.
- Added the [ApiAnimationEffect/GetEffectType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiAnimationEffect/Methods/GetEffectType.md) method to the Presentation API.
- Added the [ApiAnimationEffect/GetTriggerType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiAnimationEffect/Methods/GetTriggerType.md) method to the Presentation API.
- Added the [ApiAnimationEffect/SetTriggerType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiAnimationEffect/Methods/SetTriggerType.md) method to the Presentation API.
- Added the [ApiAnimationEffect/GetDuration](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiAnimationEffect/Methods/GetDuration.md) method to the Presentation API.
- Added the [ApiAnimationEffect/SetDuration](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiAnimationEffect/Methods/SetDuration.md) method to the Presentation API.
- Added the [ApiAnimationEffect/GetDelay](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiAnimationEffect/Methods/GetDelay.md) method to the Presentation API.
- Added the [ApiAnimationEffect/SetDelay](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiAnimationEffect/Methods/SetDelay.md) method to the Presentation API.
- Added the [ApiAnimationEffect/GetShape](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiAnimationEffect/Methods/GetShape.md) method to the Presentation API.
- Added the [ApiAnimationEffect/GetRepeatCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiAnimationEffect/Methods/GetRepeatCount.md) method to the Presentation API.
- Added the [ApiAnimationEffect/SetRepeatCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiAnimationEffect/Methods/SetRepeatCount.md) method to the Presentation API.
- Added the [ApiAnimationEffect/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiAnimationEffect/Methods/Delete.md) method to the Presentation API.
- Added the [ApiAnimationEffect/MoveTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiAnimationEffect/Methods/MoveTo.md) method to the Presentation API.

### Form methods

- Added the [ApiFormBase/SetLock](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormBase/Methods/SetLock.md) method to the Form API.
- Added the [ApiFormBase/GetLock](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormBase/Methods/GetLock.md) method to the Form API.
- Added the [ApiFormBase/SetLock](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetLock.md) method to the Document API.
- Added the [ApiFormBase/GetLock](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetLock.md) method to the Document API.

### Changed methods

- Updated the [Api/CreateStroke](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateStroke.md) method in Document API - added `sDash` parameter.
- Updated the [Api/CreateStroke](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/CreateStroke.md) method in Spreadsheet API - added `sDash` parameter.
- Updated the [Api/CreateStroke](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateStroke.md) method in Presentation API - added `sDash` parameter.
- Updated the [ApiDrawing/Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/Select.md) method in Document API - added `isReplace` parameter.
- Updated the [ApiDrawing/Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/Select.md) method in Spreadsheet API - added `isReplace` parameter.
- Updated the [ApiDrawing/Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/Select.md) method in Presentation API - added `isReplace` parameter.
- Updated the [ApiDrawing/SetHorPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/SetHorPosition.md) method in Document API - added `bPercent` parameter.
- Updated the [ApiDrawing/SetVerPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/SetVerPosition.md) method in Document API - added `bPercent` parameter.

### Drawing methods

- Added the [ApiDocument/GetDrawingsByName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetDrawingsByName.md) method to the Document API.
- Added the [ApiDrawing/GetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/GetFlipH.md) method to the Document API.
- Added the [ApiDrawing/GetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/GetFlipV.md) method to the Document API.
- Added the [ApiDrawing/Unselect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/Unselect.md) method to the Document API.
- Added the [ApiDrawing/SetRelativeHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/SetRelativeHeight.md) method to the Document API.
- Added the [ApiDrawing/SetRelativeWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/SetRelativeWidth.md) method to the Document API.

- Added the [ApiWorkbook/GetDrawingsByName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/GetDrawingsByName.md) method to the Spreadsheet API.
- Added the [ApiDrawing/GetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/GetFlipH.md) method to the Spreadsheet API.
- Added the [ApiDrawing/GetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/GetFlipV.md) method to the Spreadsheet API.
- Added the [ApiDrawing/Unselect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/Unselect.md) method to the Spreadsheet API.
- Added the [ApiWorksheet/GetSelectedShapes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/GetSelectedShapes.md) method to the Spreadsheet API.
- Added the [ApiWorksheet/GetSelectedDrawings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/GetSelectedDrawings.md) method to the Spreadsheet API.
- Added the [ApiDrawing/Fill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/Fill.md) method to the Spreadsheet API.
- Added the [ApiDrawing/SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/SetOutLine.md) method to the Spreadsheet API.

- Added the [ApiPresentation/GetDrawingsByName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetDrawingsByName.md) method to the Presentation API.
- Added the [ApiDrawing/GetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/GetFlipH.md) method to the Presentation API.
- Added the [ApiDrawing/GetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/GetFlipV.md) method to the Presentation API.
- Added the [ApiDrawing/Unselect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/Unselect.md) method to the Presentation API.
- Added the [ApiDrawing/Fill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/Fill.md) method to the Presentation API.
- Added the [ApiDrawing/SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/SetOutLine.md) method to the Presentation API.
- Added the [ApiShape/SetPaddings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/SetPaddings.md) method to the Presentation API.

### ApiTable methods

- Added the [ApiTable/SetSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/SetSize.md) method to the Presentation API.

### ApiChart methods

- Added the [ApiChart/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/GetTitle.md) method to the Document API.
- Added the [ApiChart/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/GetTitle.md) method to the Spreadsheet API.
- Added the [ApiChart/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/GetTitle.md) method to the Presentation API.

### PDF methods

- Added the PDF API.

#### Api methods

- Added the [Api/CentimetersToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CentimetersToPoints.md) method to the PDF API.
- Added the [Api/CreateBlipFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateBlipFill.md) method to the PDF API.
- Added the [Api/CreateBullet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateBullet.md) method to the PDF API.
- Added the [Api/CreateCaretAnnot](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateCaretAnnot.md) method to the PDF API.
- Added the [Api/CreateChart](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateChart.md) method to the PDF API.
- Added the [Api/CreateCheckboxField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateCheckboxField.md) method to the PDF API.
- Added the [Api/CreateCircleAnnot](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateCircleAnnot.md) method to the PDF API.
- Added the [Api/CreateComboboxField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateComboboxField.md) method to the PDF API.
- Added the [Api/CreateCustomGeometry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateCustomGeometry.md) method to the PDF API.
- Added the [Api/CreateDateField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateDateField.md) method to the PDF API.
- Added the [Api/CreateFreeTextAnnot](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateFreeTextAnnot.md) method to the PDF API.
- Added the [Api/CreateGradientStop](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateGradientStop.md) method to the PDF API.
- Added the [Api/CreateHighlightAnnot](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateHighlightAnnot.md) method to the PDF API.
- Added the [Api/CreateImage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateImage.md) method to the PDF API.
- Added the [Api/CreateImageField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateImageField.md) method to the PDF API.
- Added the [Api/CreateInkAnnot](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateInkAnnot.md) method to the PDF API.
- Added the [Api/CreateLineAnnot](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateLineAnnot.md) method to the PDF API.
- Added the [Api/CreateLinearGradientFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateLinearGradientFill.md) method to the PDF API.
- Added the [Api/CreateListboxField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateListboxField.md) method to the PDF API.
- Added the [Api/CreateNoFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateNoFill.md) method to the PDF API.
- Added the [Api/CreateNumbering](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateNumbering.md) method to the PDF API.
- Added the [Api/CreateParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateParagraph.md) method to the PDF API.
- Added the [Api/CreatePatternFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreatePatternFill.md) method to the PDF API.
- Added the [Api/CreatePolyLineAnnot](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreatePolyLineAnnot.md) method to the PDF API.
- Added the [Api/CreatePolygonAnnot](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreatePolygonAnnot.md) method to the PDF API.
- Added the [Api/CreatePresetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreatePresetColor.md) method to the PDF API.
- Added the [Api/CreatePresetGeometry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreatePresetGeometry.md) method to the PDF API.
- Added the [Api/CreateRGBColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateRGBColor.md) method to the PDF API.
- Added the [Api/CreateRadialGradientFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateRadialGradientFill.md) method to the PDF API.
- Added the [Api/CreateRadiobuttonField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateRadiobuttonField.md) method to the PDF API.
- Added the [Api/CreateRedactAnnot](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateRedactAnnot.md) method to the PDF API.
- Added the [Api/CreateRichParaPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateRichParaPr.md) method to the PDF API.
- Added the [Api/CreateRichParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateRichParagraph.md) method to the PDF API.
- Added the [Api/CreateRichRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateRichRun.md) method to the PDF API.
- Added the [Api/CreateRichTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateRichTextPr.md) method to the PDF API.
- Added the [Api/CreateRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateRun.md) method to the PDF API.
- Added the [Api/CreateSchemeColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateSchemeColor.md) method to the PDF API.
- Added the [Api/CreateShape](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateShape.md) method to the PDF API.
- Added the [Api/CreateSolidFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateSolidFill.md) method to the PDF API.
- Added the [Api/CreateSquareAnnot](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateSquareAnnot.md) method to the PDF API.
- Added the [Api/CreateStampAnnot](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateStampAnnot.md) method to the PDF API.
- Added the [Api/CreateStrikeoutAnnot](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateStrikeoutAnnot.md) method to the PDF API.
- Added the [Api/CreateStroke](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateStroke.md) method to the PDF API.
- Added the [Api/CreateTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateTable.md) method to the PDF API.
- Added the [Api/CreateTextAnnot](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateTextAnnot.md) method to the PDF API.
- Added the [Api/CreateTextField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateTextField.md) method to the PDF API.
- Added the [Api/CreateTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateTextPr.md) method to the PDF API.
- Added the [Api/CreateUnderlineAnnot](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateUnderlineAnnot.md) method to the PDF API.
- Added the [Api/EmusToMillimeters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/EmusToMillimeters.md) method to the PDF API.
- Added the [Api/EmusToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/EmusToPoints.md) method to the PDF API.
- Added the [Api/GetDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/GetDocument.md) method to the PDF API.
- Added the [Api/GetFullName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/GetFullName.md) method to the PDF API.
- Added the [Api/InchesToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/InchesToPoints.md) method to the PDF API.
- Added the [Api/LinesToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/LinesToPoints.md) method to the PDF API.
- Added the [Api/MillimetersToEmus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/MillimetersToEmus.md) method to the PDF API.
- Added the [Api/MillimetersToPixels](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/MillimetersToPixels.md) method to the PDF API.
- Added the [Api/MillimetersToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/MillimetersToPoints.md) method to the PDF API.
- Added the [Api/PicasToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/PicasToPoints.md) method to the PDF API.
- Added the [Api/PixelsToEmus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/PixelsToEmus.md) method to the PDF API.
- Added the [Api/PixelsToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/PixelsToPoints.md) method to the PDF API.
- Added the [Api/PointsToCentimeters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/PointsToCentimeters.md) method to the PDF API.
- Added the [Api/PointsToEmus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/PointsToEmus.md) method to the PDF API.
- Added the [Api/PointsToInches](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/PointsToInches.md) method to the PDF API.
- Added the [Api/PointsToLines](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/PointsToLines.md) method to the PDF API.
- Added the [Api/PointsToMillimeters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/PointsToMillimeters.md) method to the PDF API.
- Added the [Api/PointsToPicas](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/PointsToPicas.md) method to the PDF API.
- Added the [Api/PointsToPixels](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/PointsToPixels.md) method to the PDF API.
- Added the [Api/PointsToTwips](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/PointsToTwips.md) method to the PDF API.
- Added the [Api/TwipsToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/TwipsToPoints.md) method to the PDF API.

#### ApiBaseAnnotation methods

- Added the [ApiBaseAnnotation/AddReply](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/AddReply.md) method to the PDF API.
- Added the [ApiBaseAnnotation/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/Delete.md) method to the PDF API.
- Added the [ApiBaseAnnotation/GetAuthorName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetAuthorName.md) method to the PDF API.
- Added the [ApiBaseAnnotation/GetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetBorderColor.md) method to the PDF API.
- Added the [ApiBaseAnnotation/GetBorderEffectIntensity](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetBorderEffectIntensity.md) method to the PDF API.
- Added the [ApiBaseAnnotation/GetBorderEffectStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetBorderEffectStyle.md) method to the PDF API.
- Added the [ApiBaseAnnotation/GetBorderStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetBorderStyle.md) method to the PDF API.
- Added the [ApiBaseAnnotation/GetBorderWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetBorderWidth.md) method to the PDF API.
- Added the [ApiBaseAnnotation/GetContents](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetContents.md) method to the PDF API.
- Added the [ApiBaseAnnotation/GetCreationDate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetCreationDate.md) method to the PDF API.
- Added the [ApiBaseAnnotation/GetDashPattern](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetDashPattern.md) method to the PDF API.
- Added the [ApiBaseAnnotation/GetDisplay](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetDisplay.md) method to the PDF API.
- Added the [ApiBaseAnnotation/GetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetFillColor.md) method to the PDF API.
- Added the [ApiBaseAnnotation/GetModDate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetModDate.md) method to the PDF API.
- Added the [ApiBaseAnnotation/GetOpacity](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetOpacity.md) method to the PDF API.
- Added the [ApiBaseAnnotation/GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetPosition.md) method to the PDF API.
- Added the [ApiBaseAnnotation/GetRect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetRect.md) method to the PDF API.
- Added the [ApiBaseAnnotation/GetReplies](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetReplies.md) method to the PDF API.
- Added the [ApiBaseAnnotation/GetSubject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetSubject.md) method to the PDF API.
- Added the [ApiBaseAnnotation/GetUniqueName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetUniqueName.md) method to the PDF API.
- Added the [ApiBaseAnnotation/SetAuthorName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetAuthorName.md) method to the PDF API.
- Added the [ApiBaseAnnotation/SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetBorderColor.md) method to the PDF API.
- Added the [ApiBaseAnnotation/SetBorderEffectIntensity](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetBorderEffectIntensity.md) method to the PDF API.
- Added the [ApiBaseAnnotation/SetBorderEffectStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetBorderEffectStyle.md) method to the PDF API.
- Added the [ApiBaseAnnotation/SetBorderStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetBorderStyle.md) method to the PDF API.
- Added the [ApiBaseAnnotation/SetBorderWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetBorderWidth.md) method to the PDF API.
- Added the [ApiBaseAnnotation/SetContents](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetContents.md) method to the PDF API.
- Added the [ApiBaseAnnotation/SetCreationDate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetCreationDate.md) method to the PDF API.
- Added the [ApiBaseAnnotation/SetDashPattern](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetDashPattern.md) method to the PDF API.
- Added the [ApiBaseAnnotation/SetDisplay](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetDisplay.md) method to the PDF API.
- Added the [ApiBaseAnnotation/SetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetFillColor.md) method to the PDF API.
- Added the [ApiBaseAnnotation/SetModDate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetModDate.md) method to the PDF API.
- Added the [ApiBaseAnnotation/SetOpacity](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetOpacity.md) method to the PDF API.
- Added the [ApiBaseAnnotation/SetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetPosition.md) method to the PDF API.
- Added the [ApiBaseAnnotation/SetRect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetRect.md) method to the PDF API.
- Added the [ApiBaseAnnotation/SetSubject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetSubject.md) method to the PDF API.
- Added the [ApiBaseAnnotation/SetUniqueName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetUniqueName.md) method to the PDF API.

#### ApiBaseField methods

- Added the [ApiBaseField/AddWidget](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseField/Methods/AddWidget.md) method to the PDF API.
- Added the [ApiBaseField/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseField/Methods/Delete.md) method to the PDF API.
- Added the [ApiBaseField/GetAllWidgets](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseField/Methods/GetAllWidgets.md) method to the PDF API.
- Added the [ApiBaseField/GetFullName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseField/Methods/GetFullName.md) method to the PDF API.
- Added the [ApiBaseField/GetPartialName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseField/Methods/GetPartialName.md) method to the PDF API.
- Added the [ApiBaseField/GetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseField/Methods/GetValue.md) method to the PDF API.
- Added the [ApiBaseField/IsReadOnly](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseField/Methods/IsReadOnly.md) method to the PDF API.
- Added the [ApiBaseField/IsRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseField/Methods/IsRequired.md) method to the PDF API.
- Added the [ApiBaseField/SetFullName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseField/Methods/SetFullName.md) method to the PDF API.
- Added the [ApiBaseField/SetPartialName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseField/Methods/SetPartialName.md) method to the PDF API.
- Added the [ApiBaseField/SetReadOnly](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseField/Methods/SetReadOnly.md) method to the PDF API.
- Added the [ApiBaseField/SetRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseField/Methods/SetRequired.md) method to the PDF API.
- Added the [ApiBaseField/SetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseField/Methods/SetValue.md) method to the PDF API.

#### ApiBaseListField methods

- Added the [ApiBaseListField/AddOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseListField/Methods/AddOption.md) method to the PDF API.
- Added the [ApiBaseListField/GetOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseListField/Methods/GetOption.md) method to the PDF API.
- Added the [ApiBaseListField/GetOptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseListField/Methods/GetOptions.md) method to the PDF API.
- Added the [ApiBaseListField/GetValueIndexes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseListField/Methods/GetValueIndexes.md) method to the PDF API.
- Added the [ApiBaseListField/IsCommitOnSelChange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseListField/Methods/IsCommitOnSelChange.md) method to the PDF API.
- Added the [ApiBaseListField/MoveOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseListField/Methods/MoveOption.md) method to the PDF API.
- Added the [ApiBaseListField/RemoveOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseListField/Methods/RemoveOption.md) method to the PDF API.
- Added the [ApiBaseListField/SetCommitOnSelChange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseListField/Methods/SetCommitOnSelChange.md) method to the PDF API.
- Added the [ApiBaseListField/SetValueIndexes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseListField/Methods/SetValueIndexes.md) method to the PDF API.

#### ApiBaseMarkupAnnotation methods

- Added the [ApiBaseMarkupAnnotation/GetQuads](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseMarkupAnnotation/Methods/GetQuads.md) method to the PDF API.
- Added the [ApiBaseMarkupAnnotation/SetQuads](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseMarkupAnnotation/Methods/SetQuads.md) method to the PDF API.

#### ApiBaseWidget methods

- Added the [ApiBaseWidget/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/Delete.md) method to the PDF API.
- Added the [ApiBaseWidget/GetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/GetBackgroundColor.md) method to the PDF API.
- Added the [ApiBaseWidget/GetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/GetBorderColor.md) method to the PDF API.
- Added the [ApiBaseWidget/GetBorderStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/GetBorderStyle.md) method to the PDF API.
- Added the [ApiBaseWidget/GetBorderWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/GetBorderWidth.md) method to the PDF API.
- Added the [ApiBaseWidget/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiBaseWidget/GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/GetPosition.md) method to the PDF API.
- Added the [ApiBaseWidget/GetRect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/GetRect.md) method to the PDF API.
- Added the [ApiBaseWidget/GetTextColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/GetTextColor.md) method to the PDF API.
- Added the [ApiBaseWidget/GetTextSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/GetTextSize.md) method to the PDF API.
- Added the [ApiBaseWidget/IsAutoFit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/IsAutoFit.md) method to the PDF API.
- Added the [ApiBaseWidget/SetAutoFit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/SetAutoFit.md) method to the PDF API.
- Added the [ApiBaseWidget/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/SetBackgroundColor.md) method to the PDF API.
- Added the [ApiBaseWidget/SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/SetBorderColor.md) method to the PDF API.
- Added the [ApiBaseWidget/SetBorderStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/SetBorderStyle.md) method to the PDF API.
- Added the [ApiBaseWidget/SetBorderWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/SetBorderWidth.md) method to the PDF API.
- Added the [ApiBaseWidget/SetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/SetPosition.md) method to the PDF API.
- Added the [ApiBaseWidget/SetRect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/SetRect.md) method to the PDF API.
- Added the [ApiBaseWidget/SetTextColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/SetTextColor.md) method to the PDF API.
- Added the [ApiBaseWidget/SetTextSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/SetTextSize.md) method to the PDF API.

#### ApiBullet methods

- Added the [ApiBullet/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBullet/Methods/GetClassType.md) method to the PDF API.

#### ApiButtonField methods

- Added the [ApiButtonField/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonField/Methods/GetClassType.md) method to the PDF API.

#### ApiButtonWidget methods

- Added the [ApiButtonWidget/GetBehavior](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetBehavior.md) method to the PDF API.
- Added the [ApiButtonWidget/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiButtonWidget/GetIconXPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetIconXPos.md) method to the PDF API.
- Added the [ApiButtonWidget/GetIconYPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetIconYPos.md) method to the PDF API.
- Added the [ApiButtonWidget/GetLabel](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetLabel.md) method to the PDF API.
- Added the [ApiButtonWidget/GetLayout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetLayout.md) method to the PDF API.
- Added the [ApiButtonWidget/GetScaleHow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetScaleHow.md) method to the PDF API.
- Added the [ApiButtonWidget/GetScaleWhen](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetScaleWhen.md) method to the PDF API.
- Added the [ApiButtonWidget/IsFitBounds](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/IsFitBounds.md) method to the PDF API.
- Added the [ApiButtonWidget/SetBehavior](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetBehavior.md) method to the PDF API.
- Added the [ApiButtonWidget/SetFitBounds](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetFitBounds.md) method to the PDF API.
- Added the [ApiButtonWidget/SetIconXPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetIconXPos.md) method to the PDF API.
- Added the [ApiButtonWidget/SetIconYPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetIconYPos.md) method to the PDF API.
- Added the [ApiButtonWidget/SetImage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetImage.md) method to the PDF API.
- Added the [ApiButtonWidget/SetLabel](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetLabel.md) method to the PDF API.
- Added the [ApiButtonWidget/SetLayout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetLayout.md) method to the PDF API.
- Added the [ApiButtonWidget/SetScaleHow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetScaleHow.md) method to the PDF API.
- Added the [ApiButtonWidget/SetScaleWhen](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetScaleWhen.md) method to the PDF API.

#### ApiCaretAnnotation methods

- Added the [ApiCaretAnnotation/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCaretAnnotation/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiCaretAnnotation/GetQuads](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCaretAnnotation/Methods/GetQuads.md) method to the PDF API.
- Added the [ApiCaretAnnotation/SetQuads](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCaretAnnotation/Methods/SetQuads.md) method to the PDF API.

#### ApiChart methods

- Added the [ApiChart/ApplyChartStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/ApplyChartStyle.md) method to the PDF API.
- Added the [ApiChart/GetAllSeries](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/GetAllSeries.md) method to the PDF API.
- Added the [ApiChart/GetChartType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/GetChartType.md) method to the PDF API.
- Added the [ApiChart/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiChart/GetSeries](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/GetSeries.md) method to the PDF API.
- Added the [ApiChart/RemoveSeria](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/RemoveSeria.md) method to the PDF API.
- Added the [ApiChart/SetAxisNumFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetAxisNumFormat.md) method to the PDF API.
- Added the [ApiChart/SetCategoryName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetCategoryName.md) method to the PDF API.
- Added the [ApiChart/SetDataPointFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetDataPointFill.md) method to the PDF API.
- Added the [ApiChart/SetDataPointNumFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetDataPointNumFormat.md) method to the PDF API.
- Added the [ApiChart/SetDataPointOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetDataPointOutLine.md) method to the PDF API.
- Added the [ApiChart/SetHorAxisLabelsFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetHorAxisLabelsFontSize.md) method to the PDF API.
- Added the [ApiChart/SetHorAxisMajorTickMark](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetHorAxisMajorTickMark.md) method to the PDF API.
- Added the [ApiChart/SetHorAxisMinorTickMark](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetHorAxisMinorTickMark.md) method to the PDF API.
- Added the [ApiChart/SetHorAxisOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetHorAxisOrientation.md) method to the PDF API.
- Added the [ApiChart/SetHorAxisTickLabelPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetHorAxisTickLabelPosition.md) method to the PDF API.
- Added the [ApiChart/SetHorAxisTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetHorAxisTitle.md) method to the PDF API.
- Added the [ApiChart/SetLegendFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetLegendFill.md) method to the PDF API.
- Added the [ApiChart/SetLegendFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetLegendFontSize.md) method to the PDF API.
- Added the [ApiChart/SetLegendOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetLegendOutLine.md) method to the PDF API.
- Added the [ApiChart/SetLegendPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetLegendPos.md) method to the PDF API.
- Added the [ApiChart/SetMajorHorizontalGridlines](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetMajorHorizontalGridlines.md) method to the PDF API.
- Added the [ApiChart/SetMajorVerticalGridlines](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetMajorVerticalGridlines.md) method to the PDF API.
- Added the [ApiChart/SetMarkerFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetMarkerFill.md) method to the PDF API.
- Added the [ApiChart/SetMarkerOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetMarkerOutLine.md) method to the PDF API.
- Added the [ApiChart/SetMinorHorizontalGridlines](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetMinorHorizontalGridlines.md) method to the PDF API.
- Added the [ApiChart/SetMinorVerticalGridlines](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetMinorVerticalGridlines.md) method to the PDF API.
- Added the [ApiChart/SetPlotAreaFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetPlotAreaFill.md) method to the PDF API.
- Added the [ApiChart/SetPlotAreaOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetPlotAreaOutLine.md) method to the PDF API.
- Added the [ApiChart/SetSeriaName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetSeriaName.md) method to the PDF API.
- Added the [ApiChart/SetSeriaNumFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetSeriaNumFormat.md) method to the PDF API.
- Added the [ApiChart/SetSeriaValues](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetSeriaValues.md) method to the PDF API.
- Added the [ApiChart/SetSeriesFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetSeriesFill.md) method to the PDF API.
- Added the [ApiChart/SetSeriesOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetSeriesOutLine.md) method to the PDF API.
- Added the [ApiChart/SetShowDataLabels](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetShowDataLabels.md) method to the PDF API.
- Added the [ApiChart/SetShowPointDataLabel](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetShowPointDataLabel.md) method to the PDF API.
- Added the [ApiChart/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetTitle.md) method to the PDF API.
- Added the [ApiChart/SetTitleFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetTitleFill.md) method to the PDF API.
- Added the [ApiChart/SetTitleOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetTitleOutLine.md) method to the PDF API.
- Added the [ApiChart/SetVerAxisOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetVerAxisOrientation.md) method to the PDF API.
- Added the [ApiChart/SetVerAxisTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetVerAxisTitle.md) method to the PDF API.
- Added the [ApiChart/SetVertAxisLabelsFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetVertAxisLabelsFontSize.md) method to the PDF API.
- Added the [ApiChart/SetVertAxisMajorTickMark](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetVertAxisMajorTickMark.md) method to the PDF API.
- Added the [ApiChart/SetVertAxisMinorTickMark](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetVertAxisMinorTickMark.md) method to the PDF API.
- Added the [ApiChart/SetVertAxisTickLabelPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetVertAxisTickLabelPosition.md) method to the PDF API.
- Added the [ApiChart/SetXValues](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChart/Methods/SetXValues.md) method to the PDF API.

#### ApiChartSeries methods

- Added the [ApiChartSeries/ChangeChartType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChartSeries/Methods/ChangeChartType.md) method to the PDF API.
- Added the [ApiChartSeries/GetChartType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChartSeries/Methods/GetChartType.md) method to the PDF API.
- Added the [ApiChartSeries/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiChartSeries/Methods/GetClassType.md) method to the PDF API.

#### ApiCheckboxField methods

- Added the [ApiCheckboxField/AddOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxField/Methods/AddOption.md) method to the PDF API.
- Added the [ApiCheckboxField/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxField/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiCheckboxField/IsToggleToOff](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxField/Methods/IsToggleToOff.md) method to the PDF API.
- Added the [ApiCheckboxField/SetToggleToOff](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxField/Methods/SetToggleToOff.md) method to the PDF API.

#### ApiCheckboxWidget methods

- Added the [ApiCheckboxWidget/GetCheckStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxWidget/Methods/GetCheckStyle.md) method to the PDF API.
- Added the [ApiCheckboxWidget/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxWidget/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiCheckboxWidget/GetExportValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxWidget/Methods/GetExportValue.md) method to the PDF API.
- Added the [ApiCheckboxWidget/IsChecked](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxWidget/Methods/IsChecked.md) method to the PDF API.
- Added the [ApiCheckboxWidget/IsCheckedByDefault](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxWidget/Methods/IsCheckedByDefault.md) method to the PDF API.
- Added the [ApiCheckboxWidget/SetCheckStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxWidget/Methods/SetCheckStyle.md) method to the PDF API.
- Added the [ApiCheckboxWidget/SetChecked](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxWidget/Methods/SetChecked.md) method to the PDF API.
- Added the [ApiCheckboxWidget/SetCheckedByDefault](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxWidget/Methods/SetCheckedByDefault.md) method to the PDF API.
- Added the [ApiCheckboxWidget/SetExportValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxWidget/Methods/SetExportValue.md) method to the PDF API.

#### ApiCircleAnnotation methods

- Added the [ApiCircleAnnotation/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCircleAnnotation/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiCircleAnnotation/GetRectDiff](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCircleAnnotation/Methods/GetRectDiff.md) method to the PDF API.
- Added the [ApiCircleAnnotation/SetRectDiff](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCircleAnnotation/Methods/SetRectDiff.md) method to the PDF API.

#### ApiColor methods

- Added the [ApiColor/FromJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor/Methods/FromJSON.md) method to the PDF API.
- Added the [ApiColor/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiColor/GetHex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor/Methods/GetHex.md) method to the PDF API.
- Added the [ApiColor/GetRGB](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor/Methods/GetRGB.md) method to the PDF API.
- Added the [ApiColor/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor/Methods/ToJSON.md) method to the PDF API.

#### ApiComboboxField methods

- Added the [ApiComboboxField/AddOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/AddOption.md) method to the PDF API.
- Added the [ApiComboboxField/ClearFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/ClearFormat.md) method to the PDF API.
- Added the [ApiComboboxField/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiComboboxField/GetOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetOption.md) method to the PDF API.
- Added the [ApiComboboxField/GetOptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetOptions.md) method to the PDF API.
- Added the [ApiComboboxField/GetValueIndexes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetValueIndexes.md) method to the PDF API.
- Added the [ApiComboboxField/IsCommitOnSelChange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/IsCommitOnSelChange.md) method to the PDF API.
- Added the [ApiComboboxField/IsEditable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/IsEditable.md) method to the PDF API.
- Added the [ApiComboboxField/MoveOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/MoveOption.md) method to the PDF API.
- Added the [ApiComboboxField/RemoveOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/RemoveOption.md) method to the PDF API.
- Added the [ApiComboboxField/SetCommitOnSelChange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetCommitOnSelChange.md) method to the PDF API.
- Added the [ApiComboboxField/SetDateFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetDateFormat.md) method to the PDF API.
- Added the [ApiComboboxField/SetEditable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetEditable.md) method to the PDF API.
- Added the [ApiComboboxField/SetMask](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetMask.md) method to the PDF API.
- Added the [ApiComboboxField/SetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetNumberFormat.md) method to the PDF API.
- Added the [ApiComboboxField/SetPercentageFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetPercentageFormat.md) method to the PDF API.
- Added the [ApiComboboxField/SetRegularExp](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetRegularExp.md) method to the PDF API.
- Added the [ApiComboboxField/SetSpecialFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetSpecialFormat.md) method to the PDF API.
- Added the [ApiComboboxField/SetTimeFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetTimeFormat.md) method to the PDF API.
- Added the [ApiComboboxField/SetValidateRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetValidateRange.md) method to the PDF API.
- Added the [ApiComboboxField/SetValueIndexes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetValueIndexes.md) method to the PDF API.

#### ApiDocument methods

- Added the [ApiDocument/AddPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/AddPage.md) method to the PDF API.
- Added the [ApiDocument/ApplyRedact](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/ApplyRedact.md) method to the PDF API.
- Added the [ApiDocument/GetAllFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetAllFields.md) method to the PDF API.
- Added the [ApiDocument/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiDocument/GetFieldByName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetFieldByName.md) method to the PDF API.
- Added the [ApiDocument/GetPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetPage.md) method to the PDF API.
- Added the [ApiDocument/GetPagesCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/GetPagesCount.md) method to the PDF API.
- Added the [ApiDocument/RemovePage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/RemovePage.md) method to the PDF API.
- Added the [ApiDocument/SearchAndRedact](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument/Methods/SearchAndRedact.md) method to the PDF API.

#### ApiDocumentContent methods

- Added the [ApiDocumentContent/AddElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/AddElement.md) method to the PDF API.
- Added the [ApiDocumentContent/GetAllParagraphs](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/GetAllParagraphs.md) method to the PDF API.
- Added the [ApiDocumentContent/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiDocumentContent/GetCurrentParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/GetCurrentParagraph.md) method to the PDF API.
- Added the [ApiDocumentContent/GetCurrentRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/GetCurrentRun.md) method to the PDF API.
- Added the [ApiDocumentContent/GetElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/GetElement.md) method to the PDF API.
- Added the [ApiDocumentContent/GetElementsCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/GetElementsCount.md) method to the PDF API.
- Added the [ApiDocumentContent/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/GetInternalId.md) method to the PDF API.
- Added the [ApiDocumentContent/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/GetText.md) method to the PDF API.
- Added the [ApiDocumentContent/Push](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/Push.md) method to the PDF API.
- Added the [ApiDocumentContent/RemoveAllElements](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/RemoveAllElements.md) method to the PDF API.
- Added the [ApiDocumentContent/RemoveElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent/Methods/RemoveElement.md) method to the PDF API.

#### ApiDrawing methods

- Added the [ApiDrawing/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/Copy.md) method to the PDF API.
- Added the [ApiDrawing/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/Delete.md) method to the PDF API.
- Added the [ApiDrawing/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiDrawing/GetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/GetHeight.md) method to the PDF API.
- Added the [ApiDrawing/GetParentPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/GetParentPage.md) method to the PDF API.
- Added the [ApiDrawing/GetPosX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/GetPosX.md) method to the PDF API.
- Added the [ApiDrawing/GetPosY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/GetPosY.md) method to the PDF API.
- Added the [ApiDrawing/GetRotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/GetRotation.md) method to the PDF API.
- Added the [ApiDrawing/GetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/GetWidth.md) method to the PDF API.
- Added the [ApiDrawing/Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/Select.md) method to the PDF API.
- Added the [ApiDrawing/SetPosX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/SetPosX.md) method to the PDF API.
- Added the [ApiDrawing/SetPosY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/SetPosY.md) method to the PDF API.
- Added the [ApiDrawing/SetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/SetPosition.md) method to the PDF API.
- Added the [ApiDrawing/SetRotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/SetRotation.md) method to the PDF API.
- Added the [ApiDrawing/SetSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing/Methods/SetSize.md) method to the PDF API.

#### ApiFill methods

- Added the [ApiFill/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiFill/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiFill/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiFill/Methods/GetType.md) method to the PDF API.

#### ApiFreeTextAnnotation methods

- Added the [ApiFreeTextAnnotation/GetCallout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiFreeTextAnnotation/Methods/GetCallout.md) method to the PDF API.
- Added the [ApiFreeTextAnnotation/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiFreeTextAnnotation/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiFreeTextAnnotation/GetContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiFreeTextAnnotation/Methods/GetContent.md) method to the PDF API.
- Added the [ApiFreeTextAnnotation/GetIntent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiFreeTextAnnotation/Methods/GetIntent.md) method to the PDF API.
- Added the [ApiFreeTextAnnotation/GetRectDiff](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiFreeTextAnnotation/Methods/GetRectDiff.md) method to the PDF API.
- Added the [ApiFreeTextAnnotation/SetCallout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiFreeTextAnnotation/Methods/SetCallout.md) method to the PDF API.
- Added the [ApiFreeTextAnnotation/SetIntent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiFreeTextAnnotation/Methods/SetIntent.md) method to the PDF API.
- Added the [ApiFreeTextAnnotation/SetRectDiff](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiFreeTextAnnotation/Methods/SetRectDiff.md) method to the PDF API.

#### ApiGeometry methods

- Added the [ApiGeometry/AddAdj](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGeometry/Methods/AddAdj.md) method to the PDF API.
- Added the [ApiGeometry/AddConnectionPoint](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGeometry/Methods/AddConnectionPoint.md) method to the PDF API.
- Added the [ApiGeometry/AddGuide](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGeometry/Methods/AddGuide.md) method to the PDF API.
- Added the [ApiGeometry/AddPath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGeometry/Methods/AddPath.md) method to the PDF API.
- Added the [ApiGeometry/GetAdjValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGeometry/Methods/GetAdjValue.md) method to the PDF API.
- Added the [ApiGeometry/GetPath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGeometry/Methods/GetPath.md) method to the PDF API.
- Added the [ApiGeometry/GetPathCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGeometry/Methods/GetPathCount.md) method to the PDF API.
- Added the [ApiGeometry/GetPaths](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGeometry/Methods/GetPaths.md) method to the PDF API.
- Added the [ApiGeometry/GetPreset](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGeometry/Methods/GetPreset.md) method to the PDF API.
- Added the [ApiGeometry/IsCustom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGeometry/Methods/IsCustom.md) method to the PDF API.
- Added the [ApiGeometry/SetAdjValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGeometry/Methods/SetAdjValue.md) method to the PDF API.
- Added the [ApiGeometry/SetTextRect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGeometry/Methods/SetTextRect.md) method to the PDF API.

#### ApiGradientStop methods

- Added the [ApiGradientStop/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGradientStop/Methods/GetClassType.md) method to the PDF API.

#### ApiGroup methods

- Added the [ApiGroup/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGroup/Methods/GetClassType.md) method to the PDF API.

#### ApiHighlightAnnotation methods

- Added the [ApiHighlightAnnotation/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiHighlightAnnotation/GetQuads](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetQuads.md) method to the PDF API.
- Added the [ApiHighlightAnnotation/SetQuads](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/SetQuads.md) method to the PDF API.

#### ApiHyperlink methods

- Added the [ApiHyperlink/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHyperlink/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiHyperlink/GetElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHyperlink/Methods/GetElement.md) method to the PDF API.
- Added the [ApiHyperlink/GetElementsCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHyperlink/Methods/GetElementsCount.md) method to the PDF API.
- Added the [ApiHyperlink/GetLinkedText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHyperlink/Methods/GetLinkedText.md) method to the PDF API.
- Added the [ApiHyperlink/GetScreenTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHyperlink/Methods/GetScreenTipText.md) method to the PDF API.
- Added the [ApiHyperlink/SetLink](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHyperlink/Methods/SetLink.md) method to the PDF API.
- Added the [ApiHyperlink/SetScreenTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHyperlink/Methods/SetScreenTipText.md) method to the PDF API.

#### ApiImage methods

- Added the [ApiImage/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetClassType.md) method to the PDF API.

#### ApiInkAnnotation methods

- Added the [ApiInkAnnotation/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiInkAnnotation/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiInkAnnotation/GetPathList](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiInkAnnotation/Methods/GetPathList.md) method to the PDF API.
- Added the [ApiInkAnnotation/SetPathList](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiInkAnnotation/Methods/SetPathList.md) method to the PDF API.

#### ApiLineAnnotation methods

- Added the [ApiLineAnnotation/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiLineAnnotation/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiLineAnnotation/GetEndPoint](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiLineAnnotation/Methods/GetEndPoint.md) method to the PDF API.
- Added the [ApiLineAnnotation/GetEndStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiLineAnnotation/Methods/GetEndStyle.md) method to the PDF API.
- Added the [ApiLineAnnotation/GetStartPoint](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiLineAnnotation/Methods/GetStartPoint.md) method to the PDF API.
- Added the [ApiLineAnnotation/GetStartStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiLineAnnotation/Methods/GetStartStyle.md) method to the PDF API.
- Added the [ApiLineAnnotation/SetEndPoint](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiLineAnnotation/Methods/SetEndPoint.md) method to the PDF API.
- Added the [ApiLineAnnotation/SetEndStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiLineAnnotation/Methods/SetEndStyle.md) method to the PDF API.
- Added the [ApiLineAnnotation/SetStartPoint](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiLineAnnotation/Methods/SetStartPoint.md) method to the PDF API.
- Added the [ApiLineAnnotation/SetStartStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiLineAnnotation/Methods/SetStartStyle.md) method to the PDF API.

#### ApiListboxField methods

- Added the [ApiListboxField/AddOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/AddOption.md) method to the PDF API.
- Added the [ApiListboxField/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiListboxField/GetOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/GetOption.md) method to the PDF API.
- Added the [ApiListboxField/GetOptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/GetOptions.md) method to the PDF API.
- Added the [ApiListboxField/GetValueIndexes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/GetValueIndexes.md) method to the PDF API.
- Added the [ApiListboxField/IsCommitOnSelChange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/IsCommitOnSelChange.md) method to the PDF API.
- Added the [ApiListboxField/IsMultipleSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/IsMultipleSelection.md) method to the PDF API.
- Added the [ApiListboxField/MoveOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/MoveOption.md) method to the PDF API.
- Added the [ApiListboxField/RemoveOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/RemoveOption.md) method to the PDF API.
- Added the [ApiListboxField/SetCommitOnSelChange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/SetCommitOnSelChange.md) method to the PDF API.
- Added the [ApiListboxField/SetMultipleSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/SetMultipleSelection.md) method to the PDF API.
- Added the [ApiListboxField/SetValueIndexes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/SetValueIndexes.md) method to the PDF API.

#### ApiPage methods

- Added the [ApiPage/AddObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage/Methods/AddObject.md) method to the PDF API.
- Added the [ApiPage/GetAllAnnots](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage/Methods/GetAllAnnots.md) method to the PDF API.
- Added the [ApiPage/GetAllDrawings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage/Methods/GetAllDrawings.md) method to the PDF API.
- Added the [ApiPage/GetAllWidgets](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage/Methods/GetAllWidgets.md) method to the PDF API.
- Added the [ApiPage/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiPage/GetIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage/Methods/GetIndex.md) method to the PDF API.
- Added the [ApiPage/GetRotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage/Methods/GetRotation.md) method to the PDF API.
- Added the [ApiPage/GetSelectedText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage/Methods/GetSelectedText.md) method to the PDF API.
- Added the [ApiPage/GetSelectionQuads](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage/Methods/GetSelectionQuads.md) method to the PDF API.
- Added the [ApiPage/RecognizeContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage/Methods/RecognizeContent.md) method to the PDF API.
- Added the [ApiPage/Search](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage/Methods/Search.md) method to the PDF API.
- Added the [ApiPage/SetRotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage/Methods/SetRotation.md) method to the PDF API.
- Added the [ApiPage/SetSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage/Methods/SetSelection.md) method to the PDF API.

#### ApiParaPr methods

- Added the [ApiParaPr/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiParaPr/GetIndFirstLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/GetIndFirstLine.md) method to the PDF API.
- Added the [ApiParaPr/GetIndLeft](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/GetIndLeft.md) method to the PDF API.
- Added the [ApiParaPr/GetIndRight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/GetIndRight.md) method to the PDF API.
- Added the [ApiParaPr/GetJc](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/GetJc.md) method to the PDF API.
- Added the [ApiParaPr/GetOutlineLvl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/GetOutlineLvl.md) method to the PDF API.
- Added the [ApiParaPr/GetSpacingAfter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/GetSpacingAfter.md) method to the PDF API.
- Added the [ApiParaPr/GetSpacingBefore](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/GetSpacingBefore.md) method to the PDF API.
- Added the [ApiParaPr/GetSpacingLineRule](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/GetSpacingLineRule.md) method to the PDF API.
- Added the [ApiParaPr/GetSpacingLineValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/GetSpacingLineValue.md) method to the PDF API.
- Added the [ApiParaPr/SetBullet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/SetBullet.md) method to the PDF API.
- Added the [ApiParaPr/SetIndFirstLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/SetIndFirstLine.md) method to the PDF API.
- Added the [ApiParaPr/SetIndLeft](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/SetIndLeft.md) method to the PDF API.
- Added the [ApiParaPr/SetIndRight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/SetIndRight.md) method to the PDF API.
- Added the [ApiParaPr/SetJc](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/SetJc.md) method to the PDF API.
- Added the [ApiParaPr/SetOutlineLvl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/SetOutlineLvl.md) method to the PDF API.
- Added the [ApiParaPr/SetSpacingAfter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/SetSpacingAfter.md) method to the PDF API.
- Added the [ApiParaPr/SetSpacingBefore](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/SetSpacingBefore.md) method to the PDF API.
- Added the [ApiParaPr/SetSpacingLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/SetSpacingLine.md) method to the PDF API.
- Added the [ApiParaPr/SetTabs](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr/Methods/SetTabs.md) method to the PDF API.

#### ApiParagraph methods

- Added the [ApiParagraph/AddElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/AddElement.md) method to the PDF API.
- Added the [ApiParagraph/AddLineBreak](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/AddLineBreak.md) method to the PDF API.
- Added the [ApiParagraph/AddTabStop](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/AddTabStop.md) method to the PDF API.
- Added the [ApiParagraph/AddText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/AddText.md) method to the PDF API.
- Added the [ApiParagraph/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/Copy.md) method to the PDF API.
- Added the [ApiParagraph/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/Delete.md) method to the PDF API.
- Added the [ApiParagraph/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiParagraph/GetElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/GetElement.md) method to the PDF API.
- Added the [ApiParagraph/GetElementsCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/GetElementsCount.md) method to the PDF API.
- Added the [ApiParagraph/GetFontNames](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/GetFontNames.md) method to the PDF API.
- Added the [ApiParagraph/GetIndFirstLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/GetIndFirstLine.md) method to the PDF API.
- Added the [ApiParagraph/GetIndLeft](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/GetIndLeft.md) method to the PDF API.
- Added the [ApiParagraph/GetIndRight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/GetIndRight.md) method to the PDF API.
- Added the [ApiParagraph/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/GetInternalId.md) method to the PDF API.
- Added the [ApiParagraph/GetJc](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/GetJc.md) method to the PDF API.
- Added the [ApiParagraph/GetLastRunWithText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/GetLastRunWithText.md) method to the PDF API.
- Added the [ApiParagraph/GetNext](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/GetNext.md) method to the PDF API.
- Added the [ApiParagraph/GetOutlineLvl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/GetOutlineLvl.md) method to the PDF API.
- Added the [ApiParagraph/GetParaPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/GetParaPr.md) method to the PDF API.
- Added the [ApiParagraph/GetPrevious](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/GetPrevious.md) method to the PDF API.
- Added the [ApiParagraph/GetSpacingAfter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/GetSpacingAfter.md) method to the PDF API.
- Added the [ApiParagraph/GetSpacingBefore](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/GetSpacingBefore.md) method to the PDF API.
- Added the [ApiParagraph/GetSpacingLineRule](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/GetSpacingLineRule.md) method to the PDF API.
- Added the [ApiParagraph/GetSpacingLineValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/GetSpacingLineValue.md) method to the PDF API.
- Added the [ApiParagraph/InsertParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/InsertParagraph.md) method to the PDF API.
- Added the [ApiParagraph/Last](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/Last.md) method to the PDF API.
- Added the [ApiParagraph/Push](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/Push.md) method to the PDF API.
- Added the [ApiParagraph/RemoveAllElements](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/RemoveAllElements.md) method to the PDF API.
- Added the [ApiParagraph/RemoveElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/RemoveElement.md) method to the PDF API.
- Added the [ApiParagraph/Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/Select.md) method to the PDF API.
- Added the [ApiParagraph/SetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetBold.md) method to the PDF API.
- Added the [ApiParagraph/SetBullet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetBullet.md) method to the PDF API.
- Added the [ApiParagraph/SetCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetCaps.md) method to the PDF API.
- Added the [ApiParagraph/SetDoubleStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetDoubleStrikeout.md) method to the PDF API.
- Added the [ApiParagraph/SetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetFontFamily.md) method to the PDF API.
- Added the [ApiParagraph/SetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetFontSize.md) method to the PDF API.
- Added the [ApiParagraph/SetHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetHighlight.md) method to the PDF API.
- Added the [ApiParagraph/SetIndFirstLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetIndFirstLine.md) method to the PDF API.
- Added the [ApiParagraph/SetIndLeft](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetIndLeft.md) method to the PDF API.
- Added the [ApiParagraph/SetIndRight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetIndRight.md) method to the PDF API.
- Added the [ApiParagraph/SetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetItalic.md) method to the PDF API.
- Added the [ApiParagraph/SetJc](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetJc.md) method to the PDF API.
- Added the [ApiParagraph/SetOutlineLvl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetOutlineLvl.md) method to the PDF API.
- Added the [ApiParagraph/SetSmallCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetSmallCaps.md) method to the PDF API.
- Added the [ApiParagraph/SetSpacing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetSpacing.md) method to the PDF API.
- Added the [ApiParagraph/SetSpacingAfter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetSpacingAfter.md) method to the PDF API.
- Added the [ApiParagraph/SetSpacingBefore](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetSpacingBefore.md) method to the PDF API.
- Added the [ApiParagraph/SetSpacingLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetSpacingLine.md) method to the PDF API.
- Added the [ApiParagraph/SetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetStrikeout.md) method to the PDF API.
- Added the [ApiParagraph/SetTabs](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetTabs.md) method to the PDF API.
- Added the [ApiParagraph/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetTextPr.md) method to the PDF API.
- Added the [ApiParagraph/SetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/SetUnderline.md) method to the PDF API.
- Added the [ApiParagraph/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph/Methods/ToJSON.md) method to the PDF API.

#### ApiPath methods

- Added the [ApiPath/ArcTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPath/Methods/ArcTo.md) method to the PDF API.
- Added the [ApiPath/Close](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPath/Methods/Close.md) method to the PDF API.
- Added the [ApiPath/CubicBezTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPath/Methods/CubicBezTo.md) method to the PDF API.
- Added the [ApiPath/GetCommand](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPath/Methods/GetCommand.md) method to the PDF API.
- Added the [ApiPath/GetCommandCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPath/Methods/GetCommandCount.md) method to the PDF API.
- Added the [ApiPath/GetCommands](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPath/Methods/GetCommands.md) method to the PDF API.
- Added the [ApiPath/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPath/Methods/GetFill.md) method to the PDF API.
- Added the [ApiPath/GetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPath/Methods/GetHeight.md) method to the PDF API.
- Added the [ApiPath/GetStroke](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPath/Methods/GetStroke.md) method to the PDF API.
- Added the [ApiPath/GetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPath/Methods/GetWidth.md) method to the PDF API.
- Added the [ApiPath/LineTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPath/Methods/LineTo.md) method to the PDF API.
- Added the [ApiPath/MoveTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPath/Methods/MoveTo.md) method to the PDF API.
- Added the [ApiPath/QuadBezTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPath/Methods/QuadBezTo.md) method to the PDF API.
- Added the [ApiPath/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPath/Methods/SetFill.md) method to the PDF API.
- Added the [ApiPath/SetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPath/Methods/SetHeight.md) method to the PDF API.
- Added the [ApiPath/SetStroke](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPath/Methods/SetStroke.md) method to the PDF API.
- Added the [ApiPath/SetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPath/Methods/SetWidth.md) method to the PDF API.

#### ApiPathCommand methods

- Added the [ApiPathCommand/GetHR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPathCommand/Methods/GetHR.md) method to the PDF API.
- Added the [ApiPathCommand/GetStartAngle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPathCommand/Methods/GetStartAngle.md) method to the PDF API.
- Added the [ApiPathCommand/GetSweepAngle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPathCommand/Methods/GetSweepAngle.md) method to the PDF API.
- Added the [ApiPathCommand/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPathCommand/Methods/GetType.md) method to the PDF API.
- Added the [ApiPathCommand/GetWR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPathCommand/Methods/GetWR.md) method to the PDF API.
- Added the [ApiPathCommand/GetX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPathCommand/Methods/GetX.md) method to the PDF API.
- Added the [ApiPathCommand/GetX0](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPathCommand/Methods/GetX0.md) method to the PDF API.
- Added the [ApiPathCommand/GetX1](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPathCommand/Methods/GetX1.md) method to the PDF API.
- Added the [ApiPathCommand/GetX2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPathCommand/Methods/GetX2.md) method to the PDF API.
- Added the [ApiPathCommand/GetY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPathCommand/Methods/GetY.md) method to the PDF API.
- Added the [ApiPathCommand/GetY0](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPathCommand/Methods/GetY0.md) method to the PDF API.
- Added the [ApiPathCommand/GetY1](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPathCommand/Methods/GetY1.md) method to the PDF API.
- Added the [ApiPathCommand/GetY2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPathCommand/Methods/GetY2.md) method to the PDF API.

#### ApiPolyLineAnnotation methods

- Added the [ApiPolyLineAnnotation/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolyLineAnnotation/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiPolyLineAnnotation/GetEndStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolyLineAnnotation/Methods/GetEndStyle.md) method to the PDF API.
- Added the [ApiPolyLineAnnotation/GetStartStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolyLineAnnotation/Methods/GetStartStyle.md) method to the PDF API.
- Added the [ApiPolyLineAnnotation/GetVertices](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolyLineAnnotation/Methods/GetVertices.md) method to the PDF API.
- Added the [ApiPolyLineAnnotation/SetEndStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolyLineAnnotation/Methods/SetEndStyle.md) method to the PDF API.
- Added the [ApiPolyLineAnnotation/SetStartStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolyLineAnnotation/Methods/SetStartStyle.md) method to the PDF API.
- Added the [ApiPolyLineAnnotation/SetVertices](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolyLineAnnotation/Methods/SetVertices.md) method to the PDF API.

#### ApiPolygonAnnotation methods

- Added the [ApiPolygonAnnotation/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiPolygonAnnotation/GetVertices](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetVertices.md) method to the PDF API.
- Added the [ApiPolygonAnnotation/SetVertices](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/SetVertices.md) method to the PDF API.

#### ApiPresetColor methods

- Added the [ApiPresetColor/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPresetColor/Methods/GetClassType.md) method to the PDF API.

#### ApiRGBColor methods

- Added the [ApiRGBColor/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRGBColor/Methods/GetClassType.md) method to the PDF API.

#### ApiRadiobuttonField methods

- Added the [ApiRadiobuttonField/AddOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRadiobuttonField/Methods/AddOption.md) method to the PDF API.
- Added the [ApiRadiobuttonField/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRadiobuttonField/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiRadiobuttonField/IsCheckInUnison](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRadiobuttonField/Methods/IsCheckInUnison.md) method to the PDF API.
- Added the [ApiRadiobuttonField/IsToggleToOff](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRadiobuttonField/Methods/IsToggleToOff.md) method to the PDF API.
- Added the [ApiRadiobuttonField/SetCheckInUnison](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRadiobuttonField/Methods/SetCheckInUnison.md) method to the PDF API.
- Added the [ApiRadiobuttonField/SetToggleToOff](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRadiobuttonField/Methods/SetToggleToOff.md) method to the PDF API.

#### ApiRedactAnnotation methods

- Added the [ApiRedactAnnotation/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRedactAnnotation/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiRedactAnnotation/GetQuads](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRedactAnnotation/Methods/GetQuads.md) method to the PDF API.
- Added the [ApiRedactAnnotation/SetQuads](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRedactAnnotation/Methods/SetQuads.md) method to the PDF API.

#### ApiRichContent methods

- Added the [ApiRichContent/AddElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichContent/Methods/AddElement.md) method to the PDF API.
- Added the [ApiRichContent/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichContent/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiRichContent/GetContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichContent/Methods/GetContent.md) method to the PDF API.
- Added the [ApiRichContent/GetCurrentParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichContent/Methods/GetCurrentParagraph.md) method to the PDF API.
- Added the [ApiRichContent/GetCurrentRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichContent/Methods/GetCurrentRun.md) method to the PDF API.
- Added the [ApiRichContent/GetElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichContent/Methods/GetElement.md) method to the PDF API.
- Added the [ApiRichContent/Push](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichContent/Methods/Push.md) method to the PDF API.

#### ApiRichParaPr methods

- Added the [ApiRichParaPr/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParaPr/Methods/GetClassType.md) method to the PDF API.

#### ApiRichParagraph methods

- Added the [ApiRichParagraph/AddElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/AddElement.md) method to the PDF API.
- Added the [ApiRichParagraph/AddText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/AddText.md) method to the PDF API.
- Added the [ApiRichParagraph/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/Copy.md) method to the PDF API.
- Added the [ApiRichParagraph/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiRichParagraph/GetElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetElement.md) method to the PDF API.
- Added the [ApiRichParagraph/GetNext](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetNext.md) method to the PDF API.
- Added the [ApiRichParagraph/GetParaPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetParaPr.md) method to the PDF API.
- Added the [ApiRichParagraph/GetPrevious](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/GetPrevious.md) method to the PDF API.
- Added the [ApiRichParagraph/Last](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/Last.md) method to the PDF API.
- Added the [ApiRichParagraph/Push](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/Push.md) method to the PDF API.
- Added the [ApiRichParagraph/SetParaPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/SetParaPr.md) method to the PDF API.
- Added the [ApiRichParagraph/SetReadingOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichParagraph/Methods/SetReadingOrder.md) method to the PDF API.

#### ApiRichRun methods

- Added the [ApiRichRun/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/Copy.md) method to the PDF API.
- Added the [ApiRichRun/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiRichRun/GetParentParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetParentParagraph.md) method to the PDF API.
- Added the [ApiRichRun/GetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/GetTextPr.md) method to the PDF API.
- Added the [ApiRichRun/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun/Methods/SetTextPr.md) method to the PDF API.

#### ApiRichTextPr methods

- Added the [ApiRichTextPr/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr/Methods/GetClassType.md) method to the PDF API.

#### ApiRun methods

- Added the [ApiRun/AddLineBreak](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/AddLineBreak.md) method to the PDF API.
- Added the [ApiRun/AddTabStop](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/AddTabStop.md) method to the PDF API.
- Added the [ApiRun/AddText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/AddText.md) method to the PDF API.
- Added the [ApiRun/ClearContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/ClearContent.md) method to the PDF API.
- Added the [ApiRun/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/Copy.md) method to the PDF API.
- Added the [ApiRun/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/Delete.md) method to the PDF API.
- Added the [ApiRun/GetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/GetBold.md) method to the PDF API.
- Added the [ApiRun/GetCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/GetCaps.md) method to the PDF API.
- Added the [ApiRun/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiRun/GetDoubleStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/GetDoubleStrikeout.md) method to the PDF API.
- Added the [ApiRun/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/GetFill.md) method to the PDF API.
- Added the [ApiRun/GetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/GetFontFamily.md) method to the PDF API.
- Added the [ApiRun/GetFontNames](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/GetFontNames.md) method to the PDF API.
- Added the [ApiRun/GetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/GetFontSize.md) method to the PDF API.
- Added the [ApiRun/GetHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/GetHighlight.md) method to the PDF API.
- Added the [ApiRun/GetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/GetItalic.md) method to the PDF API.
- Added the [ApiRun/GetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/GetOutLine.md) method to the PDF API.
- Added the [ApiRun/GetSmallCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/GetSmallCaps.md) method to the PDF API.
- Added the [ApiRun/GetSpacing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/GetSpacing.md) method to the PDF API.
- Added the [ApiRun/GetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/GetStrikeout.md) method to the PDF API.
- Added the [ApiRun/GetTextFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/GetTextFill.md) method to the PDF API.
- Added the [ApiRun/GetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/GetTextPr.md) method to the PDF API.
- Added the [ApiRun/GetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/GetUnderline.md) method to the PDF API.
- Added the [ApiRun/RemoveAllElements](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/RemoveAllElements.md) method to the PDF API.
- Added the [ApiRun/SetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/SetBold.md) method to the PDF API.
- Added the [ApiRun/SetCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/SetCaps.md) method to the PDF API.
- Added the [ApiRun/SetDoubleStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/SetDoubleStrikeout.md) method to the PDF API.
- Added the [ApiRun/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/SetFill.md) method to the PDF API.
- Added the [ApiRun/SetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/SetFontFamily.md) method to the PDF API.
- Added the [ApiRun/SetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/SetFontSize.md) method to the PDF API.
- Added the [ApiRun/SetHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/SetHighlight.md) method to the PDF API.
- Added the [ApiRun/SetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/SetItalic.md) method to the PDF API.
- Added the [ApiRun/SetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/SetLanguage.md) method to the PDF API.
- Added the [ApiRun/SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/SetOutLine.md) method to the PDF API.
- Added the [ApiRun/SetSmallCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/SetSmallCaps.md) method to the PDF API.
- Added the [ApiRun/SetSpacing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/SetSpacing.md) method to the PDF API.
- Added the [ApiRun/SetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/SetStrikeout.md) method to the PDF API.
- Added the [ApiRun/SetTextFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/SetTextFill.md) method to the PDF API.
- Added the [ApiRun/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/SetTextPr.md) method to the PDF API.
- Added the [ApiRun/SetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/SetUnderline.md) method to the PDF API.
- Added the [ApiRun/SetVertAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun/Methods/SetVertAlign.md) method to the PDF API.

#### ApiSchemeColor methods

- Added the [ApiSchemeColor/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSchemeColor/Methods/GetClassType.md) method to the PDF API.

#### ApiShape methods

- Added the [ApiShape/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiShape/GetContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/GetContent.md) method to the PDF API.
- Added the [ApiShape/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/GetFill.md) method to the PDF API.
- Added the [ApiShape/GetGeometry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/GetGeometry.md) method to the PDF API.
- Added the [ApiShape/GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/GetLine.md) method to the PDF API.
- Added the [ApiShape/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/SetFill.md) method to the PDF API.
- Added the [ApiShape/SetGeometry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/SetGeometry.md) method to the PDF API.
- Added the [ApiShape/SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/SetLine.md) method to the PDF API.
- Added the [ApiShape/SetVerticalTextAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShape/Methods/SetVerticalTextAlign.md) method to the PDF API.

#### ApiSmartArt methods

- Added the [ApiSmartArt/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSmartArt/Methods/GetClassType.md) method to the PDF API.

#### ApiSquareAnnotation methods

- Added the [ApiSquareAnnotation/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSquareAnnotation/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiSquareAnnotation/GetRectDiff](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSquareAnnotation/Methods/GetRectDiff.md) method to the PDF API.
- Added the [ApiSquareAnnotation/SetRectDiff](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSquareAnnotation/Methods/SetRectDiff.md) method to the PDF API.

#### ApiStampAnnotation methods

- Added the [ApiStampAnnotation/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStampAnnotation/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiStampAnnotation/GetRotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStampAnnotation/Methods/GetRotation.md) method to the PDF API.
- Added the [ApiStampAnnotation/GetScale](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStampAnnotation/Methods/GetScale.md) method to the PDF API.
- Added the [ApiStampAnnotation/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStampAnnotation/Methods/GetType.md) method to the PDF API.
- Added the [ApiStampAnnotation/SetRotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStampAnnotation/Methods/SetRotation.md) method to the PDF API.
- Added the [ApiStampAnnotation/SetScale](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStampAnnotation/Methods/SetScale.md) method to the PDF API.

#### ApiStrikeoutAnnotation methods

- Added the [ApiStrikeoutAnnotation/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStrikeoutAnnotation/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiStrikeoutAnnotation/GetQuads](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStrikeoutAnnotation/Methods/GetQuads.md) method to the PDF API.
- Added the [ApiStrikeoutAnnotation/SetQuads](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStrikeoutAnnotation/Methods/SetQuads.md) method to the PDF API.

#### ApiStroke methods

- Added the [ApiStroke/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStroke/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiStroke/GetDashType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStroke/Methods/GetDashType.md) method to the PDF API.
- Added the [ApiStroke/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStroke/Methods/GetFill.md) method to the PDF API.
- Added the [ApiStroke/GetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStroke/Methods/GetWidth.md) method to the PDF API.

#### ApiTable methods

- Added the [ApiTable/AddColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/AddColumn.md) method to the PDF API.
- Added the [ApiTable/AddRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/AddRow.md) method to the PDF API.
- Added the [ApiTable/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiTable/GetRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/GetRow.md) method to the PDF API.
- Added the [ApiTable/MergeCells](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/MergeCells.md) method to the PDF API.
- Added the [ApiTable/RemoveColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/RemoveColumn.md) method to the PDF API.
- Added the [ApiTable/RemoveRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/RemoveRow.md) method to the PDF API.
- Added the [ApiTable/SetShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SetShd.md) method to the PDF API.
- Added the [ApiTable/SetTableLook](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable/Methods/SetTableLook.md) method to the PDF API.

#### ApiTableCell methods

- Added the [ApiTableCell/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiTableCell/GetContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/GetContent.md) method to the PDF API.
- Added the [ApiTableCell/SetCellBorderBottom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/SetCellBorderBottom.md) method to the PDF API.
- Added the [ApiTableCell/SetCellBorderLeft](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/SetCellBorderLeft.md) method to the PDF API.
- Added the [ApiTableCell/SetCellBorderRight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/SetCellBorderRight.md) method to the PDF API.
- Added the [ApiTableCell/SetCellBorderTop](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/SetCellBorderTop.md) method to the PDF API.
- Added the [ApiTableCell/SetCellMarginBottom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/SetCellMarginBottom.md) method to the PDF API.
- Added the [ApiTableCell/SetCellMarginLeft](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/SetCellMarginLeft.md) method to the PDF API.
- Added the [ApiTableCell/SetCellMarginRight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/SetCellMarginRight.md) method to the PDF API.
- Added the [ApiTableCell/SetCellMarginTop](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/SetCellMarginTop.md) method to the PDF API.
- Added the [ApiTableCell/SetShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/SetShd.md) method to the PDF API.
- Added the [ApiTableCell/SetTextDirection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/SetTextDirection.md) method to the PDF API.
- Added the [ApiTableCell/SetVerticalAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell/Methods/SetVerticalAlign.md) method to the PDF API.

#### ApiTableRow methods

- Added the [ApiTableRow/GetCell](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow/Methods/GetCell.md) method to the PDF API.
- Added the [ApiTableRow/GetCellsCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow/Methods/GetCellsCount.md) method to the PDF API.
- Added the [ApiTableRow/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiTableRow/SetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow/Methods/SetHeight.md) method to the PDF API.

#### ApiTextAnnotation methods

- Added the [ApiTextAnnotation/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextAnnotation/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiTextAnnotation/GetIconType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextAnnotation/Methods/GetIconType.md) method to the PDF API.
- Added the [ApiTextAnnotation/SetIconType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextAnnotation/Methods/SetIconType.md) method to the PDF API.

#### ApiTextField methods

- Added the [ApiTextField/ClearFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/ClearFormat.md) method to the PDF API.
- Added the [ApiTextField/GetCharLimit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/GetCharLimit.md) method to the PDF API.
- Added the [ApiTextField/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiTextField/IsComb](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/IsComb.md) method to the PDF API.
- Added the [ApiTextField/IsMultiline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/IsMultiline.md) method to the PDF API.
- Added the [ApiTextField/IsScrollLongText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/IsScrollLongText.md) method to the PDF API.
- Added the [ApiTextField/SetCharLimit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetCharLimit.md) method to the PDF API.
- Added the [ApiTextField/SetComb](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetComb.md) method to the PDF API.
- Added the [ApiTextField/SetDateFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetDateFormat.md) method to the PDF API.
- Added the [ApiTextField/SetMask](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetMask.md) method to the PDF API.
- Added the [ApiTextField/SetMultiline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetMultiline.md) method to the PDF API.
- Added the [ApiTextField/SetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetNumberFormat.md) method to the PDF API.
- Added the [ApiTextField/SetPercentageFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetPercentageFormat.md) method to the PDF API.
- Added the [ApiTextField/SetRegularExp](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetRegularExp.md) method to the PDF API.
- Added the [ApiTextField/SetScrollLongText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetScrollLongText.md) method to the PDF API.
- Added the [ApiTextField/SetSpecialFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetSpecialFormat.md) method to the PDF API.
- Added the [ApiTextField/SetTimeFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetTimeFormat.md) method to the PDF API.
- Added the [ApiTextField/SetValidateRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetValidateRange.md) method to the PDF API.

#### ApiTextPr methods

- Added the [ApiTextPr/GetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/GetBold.md) method to the PDF API.
- Added the [ApiTextPr/GetCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/GetCaps.md) method to the PDF API.
- Added the [ApiTextPr/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiTextPr/GetDoubleStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/GetDoubleStrikeout.md) method to the PDF API.
- Added the [ApiTextPr/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/GetFill.md) method to the PDF API.
- Added the [ApiTextPr/GetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/GetFontFamily.md) method to the PDF API.
- Added the [ApiTextPr/GetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/GetFontSize.md) method to the PDF API.
- Added the [ApiTextPr/GetHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/GetHighlight.md) method to the PDF API.
- Added the [ApiTextPr/GetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/GetItalic.md) method to the PDF API.
- Added the [ApiTextPr/GetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/GetOutLine.md) method to the PDF API.
- Added the [ApiTextPr/GetSmallCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/GetSmallCaps.md) method to the PDF API.
- Added the [ApiTextPr/GetSpacing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/GetSpacing.md) method to the PDF API.
- Added the [ApiTextPr/GetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/GetStrikeout.md) method to the PDF API.
- Added the [ApiTextPr/GetTextFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/GetTextFill.md) method to the PDF API.
- Added the [ApiTextPr/GetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/GetUnderline.md) method to the PDF API.
- Added the [ApiTextPr/SetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/SetBold.md) method to the PDF API.
- Added the [ApiTextPr/SetCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/SetCaps.md) method to the PDF API.
- Added the [ApiTextPr/SetDoubleStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/SetDoubleStrikeout.md) method to the PDF API.
- Added the [ApiTextPr/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/SetFill.md) method to the PDF API.
- Added the [ApiTextPr/SetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/SetFontFamily.md) method to the PDF API.
- Added the [ApiTextPr/SetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/SetFontSize.md) method to the PDF API.
- Added the [ApiTextPr/SetHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/SetHighlight.md) method to the PDF API.
- Added the [ApiTextPr/SetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/SetItalic.md) method to the PDF API.
- Added the [ApiTextPr/SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/SetOutLine.md) method to the PDF API.
- Added the [ApiTextPr/SetSmallCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/SetSmallCaps.md) method to the PDF API.
- Added the [ApiTextPr/SetSpacing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/SetSpacing.md) method to the PDF API.
- Added the [ApiTextPr/SetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/SetStrikeout.md) method to the PDF API.
- Added the [ApiTextPr/SetTextFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/SetTextFill.md) method to the PDF API.
- Added the [ApiTextPr/SetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/SetUnderline.md) method to the PDF API.
- Added the [ApiTextPr/SetVertAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextPr/Methods/SetVertAlign.md) method to the PDF API.

#### ApiUnderlineAnnotation methods

- Added the [ApiUnderlineAnnotation/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiUnderlineAnnotation/Methods/GetClassType.md) method to the PDF API.
- Added the [ApiUnderlineAnnotation/GetQuads](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiUnderlineAnnotation/Methods/GetQuads.md) method to the PDF API.
- Added the [ApiUnderlineAnnotation/SetQuads](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiUnderlineAnnotation/Methods/SetQuads.md) method to the PDF API.

#### ApiUniColor methods

- Added the [ApiUniColor/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiUniColor/Methods/GetClassType.md) method to the PDF API.

#### ApiUnsupported methods

- Added the [ApiUnsupported/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiUnsupported/Methods/GetClassType.md) method to the PDF API.

## Version 9.2

### CheckBoxForm methods

- Added the [ApiCheckBoxForm/GetLabel](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiCheckBoxForm/Methods/GetLabel.md) method to the Form API.
- Added the [ApiCheckBoxForm/SetLabel](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiCheckBoxForm/Methods/SetLabel.md) method to the Form API.
- Added the [ApiCheckBoxForm/GetLabel](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/GetLabel.md) method to the Document API.
- Added the [ApiCheckBoxForm/SetLabel](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/SetLabel.md) method to the Document API.

### Form methods

- Added the [ApiCheckBoxForm/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiCheckBoxForm/Methods/Delete.md) method to the Form API.
- Added the [ApiCheckBoxForm/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiCheckBoxForm/Methods/GetInternalId.md) method to the Form API.
- Added the [ApiComboBoxForm/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiComboBoxForm/Methods/Delete.md) method to the Form API.
- Added the [ApiComboBoxForm/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiComboBoxForm/Methods/GetInternalId.md) method to the Form API.
- Added the [ApiComplexForm/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiComplexForm/Methods/Delete.md) method to the Form API.
- Added the [ApiComplexForm/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiComplexForm/Methods/GetInternalId.md) method to the Form API.
- Added the [ApiDateForm/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDateForm/Methods/Delete.md) method to the Form API.
- Added the [ApiDateForm/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDateForm/Methods/GetInternalId.md) method to the Form API.
- Added the [ApiFormBase/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormBase/Methods/Delete.md) method to the Form API.
- Added the [ApiFormBase/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormBase/Methods/GetInternalId.md) method to the Form API.
- Added the [ApiPictureForm/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiPictureForm/Methods/Delete.md) method to the Form API.
- Added the [ApiPictureForm/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiPictureForm/Methods/GetInternalId.md) method to the Form API.
- Added the [ApiTextForm/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiTextForm/Methods/Delete.md) method to the Form API.
- Added the [ApiTextForm/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiTextForm/Methods/GetInternalId.md) method to the Form API.
- Added the [ApiCheckBoxForm/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/Delete.md) method to the Document API.
- Added the [ApiCheckBoxForm/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/GetInternalId.md) method to the Document API.
- Added the [ApiComboBoxForm/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/Delete.md) method to the Document API.
- Added the [ApiComboBoxForm/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/GetInternalId.md) method to the Document API.
- Added the [ApiComplexForm/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/Delete.md) method to the Document API.
- Added the [ApiComplexForm/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetInternalId.md) method to the Document API.
- Added the [ApiDateForm/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/Delete.md) method to the Document API.
- Added the [ApiDateForm/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/GetInternalId.md) method to the Document API.
- Added the [ApiFormBase/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/Delete.md) method to the Document API.
- Added the [ApiFormBase/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetInternalId.md) method to the Document API.
- Added the [ApiPictureForm/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/Delete.md) method to the Document API.
- Added the [ApiPictureForm/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/GetInternalId.md) method to the Document API.
- Added the [ApiTextForm/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/Delete.md) method to the Document API.
- Added the [ApiTextForm/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetInternalId.md) method to the Document API.

### Paragraph methods

- Added the [ApiParagraph/GetFontNames](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/GetFontNames.md) method to the Presentation API.
- Added the [ApiParagraph/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/GetInternalId.md) method to the Presentation API.
- Added the [ApiParagraph/GetLastRunWithText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/GetLastRunWithText.md) method to the Presentation API.
- Added the [ApiParagraph/InsertParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/InsertParagraph.md) method to the Presentation API.
- Added the [ApiParagraph/Last](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/Last.md) method to the Presentation API.
- Added the [ApiParagraph/Push](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/Push.md) method to the Presentation API.
- Added the [ApiParagraph/SetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/SetBold.md) method to the Presentation API.
- Added the [ApiParagraph/SetCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/SetCaps.md) method to the Presentation API.
- Added the [ApiParagraph/SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/SetColor.md) method to the Presentation API.
- Added the [ApiParagraph/SetDoubleStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/SetDoubleStrikeout.md) method to the Presentation API.
- Added the [ApiParagraph/SetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/SetFontFamily.md) method to the Presentation API.
- Added the [ApiParagraph/SetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/SetFontSize.md) method to the Presentation API.
- Added the [ApiParagraph/SetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/SetItalic.md) method to the Presentation API.
- Added the [ApiParagraph/SetSmallCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/SetSmallCaps.md) method to the Presentation API.
- Added the [ApiParagraph/SetSpacing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/SetSpacing.md) method to the Presentation API.
- Added the [ApiParagraph/SetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/SetStrikeout.md) method to the Presentation API.
- Added the [ApiParagraph/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/SetTextPr.md) method to the Presentation API.
- Added the [ApiParagraph/SetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/SetUnderline.md) method to the Presentation API.
- Added the [ApiParagraph/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/ToJSON.md) method to the Presentation API.
- Added the [ApiParagraph/GetFontNames](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/GetFontNames.md) method to the Spreadsheet API.
- Added the [ApiParagraph/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/GetInternalId.md) method to the Spreadsheet API.
- Added the [ApiParagraph/GetLastRunWithText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/GetLastRunWithText.md) method to the Spreadsheet API.
- Added the [ApiParagraph/InsertParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/InsertParagraph.md) method to the Spreadsheet API.
- Added the [ApiParagraph/Last](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/Last.md) method to the Spreadsheet API.
- Added the [ApiParagraph/Push](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/Push.md) method to the Spreadsheet API.
- Added the [ApiParagraph/SetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/SetBold.md) method to the Spreadsheet API.
- Added the [ApiParagraph/SetCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/SetCaps.md) method to the Spreadsheet API.
- Added the [ApiParagraph/SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/SetColor.md) method to the Spreadsheet API.
- Added the [ApiParagraph/SetDoubleStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/SetDoubleStrikeout.md) method to the Spreadsheet API.
- Added the [ApiParagraph/SetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/SetFontFamily.md) method to the Spreadsheet API.
- Added the [ApiParagraph/SetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/SetFontSize.md) method to the Spreadsheet API.
- Added the [ApiParagraph/SetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/SetItalic.md) method to the Spreadsheet API.
- Added the [ApiParagraph/SetSmallCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/SetSmallCaps.md) method to the Spreadsheet API.
- Added the [ApiParagraph/SetSpacing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/SetSpacing.md) method to the Spreadsheet API.
- Added the [ApiParagraph/SetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/SetStrikeout.md) method to the Spreadsheet API.
- Added the [ApiParagraph/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/SetTextPr.md) method to the Spreadsheet API.
- Added the [ApiParagraph/SetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/SetUnderline.md) method to the Spreadsheet API.
- Added the [ApiParagraph/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParagraph/Methods/ToJSON.md) method to the Spreadsheet API.
- Added the [ApiParagraph/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/GetInternalId.md) method to the Document API.
- Added the [ApiParagraph/GetParaId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/GetParaId.md) method to the Document API.
- Added the [ApiParagraph/SetParaId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/SetParaId.md) method to the Document API.

### Presentation methods

- Added the [Api/EmusToMillimeters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/EmusToMillimeters.md) method to the Presentation API.
- Added the [Api/MillimetersToEmus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/MillimetersToEmus.md) method to the Presentation API.
- Added the [ApiDocumentContent/GetAllParagraphs](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDocumentContent/Methods/GetAllParagraphs.md) method to the Presentation API.
- Added the [ApiDocumentContent/GetCurrentParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDocumentContent/Methods/GetCurrentParagraph.md) method to the Presentation API.
- Added the [ApiDocumentContent/GetCurrentRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDocumentContent/Methods/GetCurrentRun.md) method to the Presentation API.
- Added the [ApiDocumentContent/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDocumentContent/Methods/GetText.md) method to the Presentation API.

### Spreadsheet methods

- Added the [Api/EmusToMillimeters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/EmusToMillimeters.md) method to the Spreadsheet API.
- Added the [Api/MillimetersToEmus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/MillimetersToEmus.md) method to the Spreadsheet API.
- Added the [ApiDocumentContent/GetAllParagraphs](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDocumentContent/Methods/GetAllParagraphs.md) method to the Spreadsheet API.
- Added the [ApiDocumentContent/GetCurrentParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDocumentContent/Methods/GetCurrentParagraph.md) method to the Spreadsheet API.
- Added the [ApiDocumentContent/GetCurrentRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDocumentContent/Methods/GetCurrentRun.md) method to the Spreadsheet API.
- Added the [ApiDocumentContent/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDocumentContent/Methods/GetText.md) method to the Spreadsheet API.

### Document methods

- Added the [Api/EmusToMillimeters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/EmusToMillimeters.md) method to the Document API.
- Added the [Api/MillimetersToEmus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/MillimetersToEmus.md) method to the Document API.
- Added the [ApiDocument/EnterText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/EnterText.md) method to the Document API.
- Added the [ApiDocument/InsertParagraphBreak](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/InsertParagraphBreak.md) method to the Document API.
- Added the [ApiDocument/MoveCursorDown](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/MoveCursorDown.md) method to the Document API.
- Added the [ApiDocument/MoveCursorLeft](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/MoveCursorLeft.md) method to the Document API.
- Added the [ApiDocument/MoveCursorRight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/MoveCursorRight.md) method to the Document API.
- Added the [ApiDocument/MoveCursorUp](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/MoveCursorUp.md) method to the Document API.
- Added the [ApiTable/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/GetInternalId.md) method to the Document API.
- Added the [ApiTableCell/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableCell/Methods/GetInternalId.md) method to the Document API.
- Added the [ApiTableRow/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableRow/Methods/GetInternalId.md) method to the Document API.

## Version 9.1

### Conditional formatting methods

- Added the [ApiFormatCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition.md) class to the Spreadsheet API.
- Added the [ApiFormatCondition/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/Delete.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/Modify](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/Modify.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/ModifyAppliesToRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/ModifyAppliesToRange.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/GetAppliesTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetAppliesTo.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/GetDateOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetDateOperator.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/GetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetFillColor.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/GetFont](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetFont.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/GetFormula1](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetFormula1.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/GetFormula2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetFormula2.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/GetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetNumberFormat.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/GetOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetOperator.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetParent.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/GetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetPriority.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/GetPTCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetPTCondition.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/GetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetScopeType.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetText.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/GetTextOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetTextOperator.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetType.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/SetBorders](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetBorders.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/SetDateOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetDateOperator.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/SetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetFillColor.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/SetFirstPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetFirstPriority.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/SetLastPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetLastPriority.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/SetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetNumberFormat.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/SetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetPriority.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/SetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetScopeType.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetText.md) method to the Spreadsheet API.
- Added the [ApiFormatCondition/SetTextOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetTextOperator.md) method to the Spreadsheet API.
- Added the [ApiFormatConditions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatConditions.md) class to the Spreadsheet API.
- Added the [ApiFormatConditions/Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatConditions/Methods/Add.md) method to the Spreadsheet API.
- Added the [ApiFormatConditions/AddAboveAverage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatConditions/Methods/AddAboveAverage.md) method to the Spreadsheet API.
- Added the [ApiFormatConditions/AddColorScale](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatConditions/Methods/AddColorScale.md) method to the Spreadsheet API.
- Added the [ApiFormatConditions/AddDatabar](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatConditions/Methods/AddDatabar.md) method to the Spreadsheet API.
- Added the [ApiFormatConditions/AddIconSetCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatConditions/Methods/AddIconSetCondition.md) method to the Spreadsheet API.
- Added the [ApiFormatConditions/AddTop10](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatConditions/Methods/AddTop10.md) method to the Spreadsheet API.
- Added the [ApiFormatConditions/AddUniqueValues](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatConditions/Methods/AddUniqueValues.md) method to the Spreadsheet API.
- Added the [ApiFormatConditions/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatConditions/Methods/Delete.md) method to the Spreadsheet API.
- Added the [ApiFormatConditions/GetCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatConditions/Methods/GetCount.md) method to the Spreadsheet API.
- Added the [ApiFormatConditions/GetItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatConditions/Methods/GetItem.md) method to the Spreadsheet API.
- Added the [ApiFormatConditions/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatConditions/Methods/GetParent.md) method to the Spreadsheet API.
- Added the [ApiRange/GetFormatConditions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/GetFormatConditions.md) method to the Spreadsheet API.
- Added the `FormatConditions` property to the [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) object of Spreadsheet API.
- Added the [XlContainsOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlContainsOperator.md) type to the simple type definitions.
- Added the [XlFormatConditionOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlFormatConditionOperator.md) type to the simple type definitions.
- Added the [XlFormatConditionType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlFormatConditionType.md) type to the simple type definitions.
- Added the [XlPivotConditionScope](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlPivotConditionScope.md) type to the simple type definitions.
- Added the [XlTimePeriods](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlTimePeriods.md) type to the simple type definitions.

### Above average methods

- Added the [ApiAboveAverage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage.md) class to the Spreadsheet API.
- Added the [ApiAboveAverage/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/Delete.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/GetAboveBelow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/GetAboveBelow.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/GetAppliesTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/GetAppliesTo.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/GetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/GetFillColor.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/GetFont](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/GetFont.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/GetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/GetNumberFormat.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/GetNumStdDev](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/GetNumStdDev.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/GetParent.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/GetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/GetPriority.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/GetPTCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/GetPTCondition.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/GetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/GetScopeType.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/GetType.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/ModifyAppliesToRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/ModifyAppliesToRange.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/SetAboveBelow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/SetAboveBelow.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/SetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/SetFillColor.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/SetFirstPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/SetFirstPriority.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/SetLastPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/SetLastPriority.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/SetNumStdDev](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/SetNumStdDev.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/SetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/SetNumberFormat.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/SetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/SetPriority.md) method to the Spreadsheet API.
- Added the [ApiAboveAverage/SetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAboveAverage/Methods/SetScopeType.md) method to the Spreadsheet API.

### Color scale methods

- Added the [ApiColorScale](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale.md) class to the Spreadsheet API.
- Added the [ApiColorScale/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/Delete.md) method to the Spreadsheet API.
- Added the [ApiColorScale/GetAppliesTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetAppliesTo.md) method to the Spreadsheet API.
- Added the [ApiColorScale/GetColorScaleCriteria](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetColorScaleCriteria.md) method to the Spreadsheet API.
- Added the [ApiColorScale/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetParent.md) method to the Spreadsheet API.
- Added the [ApiColorScale/GetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetPriority.md) method to the Spreadsheet API.
- Added the [ApiColorScale/GetPTCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetPTCondition.md) method to the Spreadsheet API.
- Added the [ApiColorScale/GetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetScopeType.md) method to the Spreadsheet API.
- Added the [ApiColorScale/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetType.md) method to the Spreadsheet API.
- Added the [ApiColorScale/ModifyAppliesToRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/ModifyAppliesToRange.md) method to the Spreadsheet API.
- Added the [ApiColorScale/SetFirstPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/SetFirstPriority.md) method to the Spreadsheet API.
- Added the [ApiColorScale/SetLastPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/SetLastPriority.md) method to the Spreadsheet API.
- Added the [ApiColorScale/SetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/SetPriority.md) method to the Spreadsheet API.
- Added the [ApiColorScale/SetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/SetScopeType.md) method to the Spreadsheet API.
- Added the [ApiColorScaleCriterion](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScaleCriterion.md) class to the Spreadsheet API.
- Added the [ApiColorScaleCriterion/GetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScaleCriterion/Methods/GetColor.md) method to the Spreadsheet API.
- Added the [ApiColorScaleCriterion/GetIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScaleCriterion/Methods/GetIndex.md) method to the Spreadsheet API.
- Added the [ApiColorScaleCriterion/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScaleCriterion/Methods/GetType.md) method to the Spreadsheet API.
- Added the [ApiColorScaleCriterion/GetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScaleCriterion/Methods/GetValue.md) method to the Spreadsheet API.
- Added the [ApiColorScaleCriterion/SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScaleCriterion/Methods/SetColor.md) method to the Spreadsheet API.
- Added the [ApiColorScaleCriterion/SetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScaleCriterion/Methods/SetType.md) method to the Spreadsheet API.
- Added the [ApiColorScaleCriterion/SetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScaleCriterion/Methods/SetValue.md) method to the Spreadsheet API.
- Added the [XlConditionValueTypes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlConditionValueTypes.md) type to the simple type definitions.

### Databar methods

- Added the [ApiDatabar](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar.md) class to the Spreadsheet API.
- Added the [ApiDatabar/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/Delete.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetAppliesTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetAppliesTo.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetAxisColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetAxisColor.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetAxisPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetAxisPosition.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetBarColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetBarColor.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetBarBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetBarBorderColor.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetBarFillType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetBarFillType.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetDirection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetDirection.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetFormula](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetFormula.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetMaxPointType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetMaxPointType.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetMaxPointValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetMaxPointValue.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetMinPointType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetMinPointType.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetMinPointValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetMinPointValue.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetNegativeBarColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetNegativeBarColor.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetNegativeBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetNegativeBorderColor.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetParent.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetPercentMax](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetPercentMax.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetPercentMin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetPercentMin.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetPriority.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetPTCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetPTCondition.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetScopeType.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetShowValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetShowValue.md) method to the Spreadsheet API.
- Added the [ApiDatabar/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/GetType.md) method to the Spreadsheet API.
- Added the [ApiDatabar/ModifyAppliesToRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/ModifyAppliesToRange.md) method to the Spreadsheet API.
- Added the [ApiDatabar/SetAxisColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetAxisColor.md) method to the Spreadsheet API.
- Added the [ApiDatabar/SetAxisPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetAxisPosition.md) method to the Spreadsheet API.
- Added the [ApiDatabar/SetBarBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetBarBorderColor.md) method to the Spreadsheet API.v
- Added the [ApiDatabar/SetBarColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetBarColor.md) method to the Spreadsheet API.
- Added the [ApiDatabar/SetBarFillType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetBarFillType.md) method to the Spreadsheet API.
- Added the [ApiDatabar/SetDirection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetDirection.md) method to the Spreadsheet API.
- Added the [ApiDatabar/SetFirstPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetFirstPriority.md) method to the Spreadsheet API.
- Added the [ApiDatabar/SetLastPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetLastPriority.md) method to the Spreadsheet API.
- Added the [ApiDatabar/SetMaxPointType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetMaxPointType.md) method to the Spreadsheet API.
- Added the [ApiDatabar/SetMaxPointValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetMaxPointValue.md) method to the Spreadsheet API.
- Added the [ApiDatabar/SetMinPointType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetMinPointType.md) method to the Spreadsheet API.
- Added the [ApiDatabar/SetMinPointValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetMinPointValue.md) method to the Spreadsheet API.
- Added the [ApiDatabar/SetNegativeBarColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetNegativeBarColor.md) method to the Spreadsheet API.
- Added the [ApiDatabar/SetNegativeBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetNegativeBorderColor.md) method to the Spreadsheet API.
- Added the [ApiDatabar/SetPercentMax](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetPercentMax.md) method to the Spreadsheet API.
- Added the [ApiDatabar/SetPercentMin](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetPercentMin.md) method to the Spreadsheet API.
- Added the [ApiDatabar/SetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetPriority.md) method to the Spreadsheet API.
- Added the [ApiDatabar/SetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetScopeType.md) method to the Spreadsheet API.
- Added the [ApiDatabar/SetShowValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDatabar/Methods/SetShowValue.md) method to the Spreadsheet API.
- Added the [XlDataBarAxisPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlDataBarAxisPosition.md) type to the simple type definitions.
- Added the [XlDataBarFillType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlDataBarFillType.md) type to the simple type definitions.
- Added the [XlReadingOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlReadingOrder.md) type to the simple type definitions.

### Icon set methods

- Added the [ApiIconCriterion](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconCriterion.md) class to the Spreadsheet API.
- Added the [ApiIconCriterion/GetIcon](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconCriterion/Methods/GetIcon.md) method to the Spreadsheet API.
- Added the [ApiIconCriterion/GetIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconCriterion/Methods/GetIndex.md) method to the Spreadsheet API.
- Added the [ApiIconCriterion/GetOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconCriterion/Methods/GetOperator.md) method to the Spreadsheet API.
- Added the [ApiIconCriterion/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconCriterion/Methods/GetType.md) method to the Spreadsheet API.
- Added the [ApiIconCriterion/GetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconCriterion/Methods/GetValue.md) method to the Spreadsheet API.
- Added the [ApiIconCriterion/SetIcon](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconCriterion/Methods/SetIcon.md) method to the Spreadsheet API.
- Added the [ApiIconCriterion/SetOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconCriterion/Methods/SetOperator.md) method to the Spreadsheet API.
- Added the [ApiIconCriterion/SetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconCriterion/Methods/SetType.md) method to the Spreadsheet API.
- Added the [ApiIconCriterion/SetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconCriterion/Methods/SetValue.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition.md) class to the Spreadsheet API.
- Added the [ApiIconSetCondition/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/Delete.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/GetAppliesTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/GetAppliesTo.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/GetFormula](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/GetFormula.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/GetIconCriteria](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/GetIconCriteria.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/GetIconSet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/GetIconSet.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/GetParent.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/GetPercentileValues](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/GetPercentileValues.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/GetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/GetPriority.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/GetPTCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/GetPTCondition.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/GetReverseOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/GetReverseOrder.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/GetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/GetScopeType.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/GetShowIconOnly](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/GetShowIconOnly.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/GetType.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/ModifyAppliesToRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/ModifyAppliesToRange.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/SetFirstPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/SetFirstPriority.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/SetIconSet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/SetIconSet.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/SetLastPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/SetLastPriority.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/SetPercentileValues](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/SetPercentileValues.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/SetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/SetPriority.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/SetReverseOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/SetReverseOrder.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/SetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/SetScopeType.md) method to the Spreadsheet API.
- Added the [ApiIconSetCondition/SetShowIconOnly](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiIconSetCondition/Methods/SetShowIconOnly.md) method to the Spreadsheet API.
- Added the [XlIcon](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlIcon.md) type to the simple type definitions.
- Added the [XlIconSet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlIconSet.md) type to the simple type definitions.

### Top 10 methods

- Added the [ApiTop10](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10.md) class to the Spreadsheet API.
- Added the [ApiTop10/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/Delete.md) method to the Spreadsheet API.
- Added the [ApiTop10/GetAppliesTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetAppliesTo.md) method to the Spreadsheet API.
- Added the [ApiTop10/GetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetFillColor.md) method to the Spreadsheet API.
- Added the [ApiTop10/GetFont](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetFont.md) method to the Spreadsheet API.
- Added the [ApiTop10/GetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetNumberFormat.md) method to the Spreadsheet API.
- Added the [ApiTop10/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetParent.md) method to the Spreadsheet API.
- Added the [ApiTop10/GetPercent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetPercent.md) method to the Spreadsheet API.
- Added the [ApiTop10/GetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetPriority.md) method to the Spreadsheet API.
- Added the [ApiTop10/GetPTCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetPTCondition.md) method to the Spreadsheet API.
- Added the [ApiTop10/GetRank](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetRank.md) method to the Spreadsheet API.
- Added the [ApiTop10/GetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetScopeType.md) method to the Spreadsheet API.
- Added the [ApiTop10/GetTopBottom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetTopBottom.md) method to the Spreadsheet API.
- Added the [ApiTop10/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetType.md) method to the Spreadsheet API.
- Added the [ApiTop10/ModifyAppliesToRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/ModifyAppliesToRange.md) method to the Spreadsheet API.
- Added the [ApiTop10/SetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetFillColor.md) method to the Spreadsheet API.
- Added the [ApiTop10/SetFirstPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetFirstPriority.md) method to the Spreadsheet API.
- Added the [ApiTop10/SetLastPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetLastPriority.md) method to the Spreadsheet API.
- Added the [ApiTop10/SetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetNumberFormat.md) method to the Spreadsheet API.
- Added the [ApiTop10/SetPercent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetPercent.md) method to the Spreadsheet API.
- Added the [ApiTop10/SetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetPriority.md) method to the Spreadsheet API.
- Added the [ApiTop10/SetRank](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetRank.md) method to the Spreadsheet API.
- Added the [ApiTop10/SetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetScopeType.md) method to the Spreadsheet API.
- Added the [ApiTop10/SetTopBottom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetTopBottom.md) method to the Spreadsheet API.
- Added the [XlTopBottom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlTopBottom.md) type to the simple type definitions.

### Unique values methods

- Added the [ApiUniqueValues](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues.md) class to the Spreadsheet API.
- Added the [ApiUniqueValues/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/Delete.md) method to the Spreadsheet API.
- Added the [ApiUniqueValues/GetAppliesTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetAppliesTo.md) method to the Spreadsheet API.
- Added the [ApiUniqueValues/GetDupeUnique](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetDupeUnique.md) method to the Spreadsheet API.
- Added the [ApiUniqueValues/GetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetFillColor.md) method to the Spreadsheet API.
- Added the [ApiUniqueValues/GetFont](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetFont.md) method to the Spreadsheet API.
- Added the [ApiUniqueValues/GetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetNumberFormat.md) method to the Spreadsheet API.
- Added the [ApiUniqueValues/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetParent.md) method to the Spreadsheet API.
- Added the [ApiUniqueValues/GetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetPriority.md) method to the Spreadsheet API.
- Added the [ApiUniqueValues/GetPTCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetPTCondition.md) method to the Spreadsheet API.
- Added the [ApiUniqueValues/GetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetScopeType.md) method to the Spreadsheet API.
- Added the [ApiUniqueValues/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetType.md) method to the Spreadsheet API.
- Added the [ApiUniqueValues/ModifyAppliesToRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/ModifyAppliesToRange.md) method to the Spreadsheet API.
- Added the [ApiUniqueValues/SetDupeUnique](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetDupeUnique.md) method to the Spreadsheet API.
- Added the [ApiUniqueValues/SetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetFillColor.md) method to the Spreadsheet API.
- Added the [ApiUniqueValues/SetFirstPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetFirstPriority.md) method to the Spreadsheet API.
- Added the [ApiUniqueValues/SetLastPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetLastPriority.md) method to the Spreadsheet API.
- Added the [ApiUniqueValues/SetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetNumberFormat.md) method to the Spreadsheet API.
- Added the [ApiUniqueValues/SetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetPriority.md) method to the Spreadsheet API.
- Added the [ApiUniqueValues/SetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetScopeType.md) method to the Spreadsheet API.
- Added the [XlDuplicateValues](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlDuplicateValues.md) type to the simple type definitions.

### Geometry methods

- Added the [Api/CreateCustomGeometry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateCustomGeometry.md) method to the Document API.
- Added the [Api/CreatePresetGeometry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreatePresetGeometry.md) method to the Document API.
- Added the [ApiGeometry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGeometry.md) class to the Document API.
- Added the [ApiGeometry/AddAdj](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGeometry/Methods/AddAdj.md) method to the Document API.
- Added the [ApiGeometry/AddConnectionPoint](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGeometry/Methods/AddConnectionPoint.md) method to the Document API.
- Added the [ApiGeometry/AddGuide](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGeometry/Methods/AddGuide.md) method to the Document API.
- Added the [ApiGeometry/AddPath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGeometry/Methods/AddPath.md) method to the Document API.
- Added the [ApiGeometry/GetAdjValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGeometry/Methods/GetAdjValue.md) method to the Document API.
- Added the [ApiGeometry/GetPath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGeometry/Methods/GetPath.md) method to the Document API.
- Added the [ApiGeometry/GetPathCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGeometry/Methods/GetPathCount.md) method to the Document API.
- Added the [ApiGeometry/GetPaths](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGeometry/Methods/GetPaths.md) method to the Document API.
- Added the [ApiGeometry/GetPreset](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGeometry/Methods/GetPreset.md) method to the Document API.
- Added the [ApiGeometry/IsCustom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGeometry/Methods/IsCustom.md) method to the Document API.
- Added the [ApiGeometry/SetAdjValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGeometry/Methods/SetAdjValue.md) method to the Document API.
- Added the [ApiGeometry/SetTextRect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGeometry/Methods/SetTextRect.md) method to the Document API.
- Added the [ApiShape/GetGeometry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape/Methods/GetGeometry.md) method to the Document API.
- Added the [ApiShape/SetGeometry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShape/Methods/SetGeometry.md) method to the Document API.
- Added the [Api/CreateCustomGeometry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/CreateCustomGeometry.md) method to the Spreadsheet API.
- Added the [Api/CreatePresetGeometry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/CreatePresetGeometry.md) method to the Spreadsheet API.
- Added the [ApiGeometry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGeometry.md) class to the Spreadsheet API.
- Added the [ApiGeometry/AddAdj](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGeometry/Methods/AddAdj.md) method to the Spreadsheet API.
- Added the [ApiGeometry/AddConnectionPoint](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGeometry/Methods/AddConnectionPoint.md) method to the Spreadsheet API.
- Added the [ApiGeometry/AddGuide](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGeometry/Methods/AddGuide.md) method to the Spreadsheet API.
- Added the [ApiGeometry/AddPath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGeometry/Methods/AddPath.md) method to the Spreadsheet API.
- Added the [ApiGeometry/GetAdjValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGeometry/Methods/GetAdjValue.md) method to the Spreadsheet API.
- Added the [ApiGeometry/GetPath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGeometry/Methods/GetPath.md) method to the Spreadsheet API.
- Added the [ApiGeometry/GetPathCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGeometry/Methods/GetPathCount.md) method to the Spreadsheet API.
- Added the [ApiGeometry/GetPaths](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGeometry/Methods/GetPaths.md) method to the Spreadsheet API.
- Added the [ApiGeometry/GetPreset](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGeometry/Methods/GetPreset.md) method to the Spreadsheet API.
- Added the [ApiGeometry/IsCustom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGeometry/Methods/IsCustom.md) method to the Spreadsheet API.
- Added the [ApiGeometry/SetAdjValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGeometry/Methods/SetAdjValue.md) method to the Spreadsheet API.
- Added the [ApiGeometry/SetTextRect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGeometry/Methods/SetTextRect.md) method to the Spreadsheet API.
- Added the [ApiShape/GetGeometry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/GetGeometry.md) method to the Spreadsheet API.
- Added the [ApiShape/SetGeometry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape/Methods/SetGeometry.md) method to the Spreadsheet API.
- Added the [Api/CreateCustomGeometry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateCustomGeometry.md) method to the Presentation API.
- Added the [Api/CreatePresetGeometry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreatePresetGeometry.md) method to the Presentation API.
- Added the [ApiGeometry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGeometry.md) class to the Presentation API.
- Added the [ApiGeometry/AddAdj](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGeometry/Methods/AddAdj.md) method to the Presentation API.
- Added the [ApiGeometry/AddConnectionPoint](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGeometry/Methods/AddConnectionPoint.md) method to the Presentation API.
- Added the [ApiGeometry/AddGuide](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGeometry/Methods/AddGuide.md) method to the Presentation API.
- Added the [ApiGeometry/AddPath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGeometry/Methods/AddPath.md) method to the Presentation API.
- Added the [ApiGeometry/GetAdjValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGeometry/Methods/GetAdjValue.md) method to the Presentation API.
- Added the [ApiGeometry/GetPath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGeometry/Methods/GetPath.md) method to the Presentation API.
- Added the [ApiGeometry/GetPathCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGeometry/Methods/GetPathCount.md) method to the Presentation API.
- Added the [ApiGeometry/GetPaths](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGeometry/Methods/GetPaths.md) method to the Presentation API.
- Added the [ApiGeometry/GetPreset](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGeometry/Methods/GetPreset.md) method to the Presentation API.
- Added the [ApiGeometry/IsCustom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGeometry/Methods/IsCustom.md) method to the Presentation API.
- Added the [ApiGeometry/SetAdjValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGeometry/Methods/SetAdjValue.md) method to the Presentation API.
- Added the [ApiGeometry/SetTextRect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGeometry/Methods/SetTextRect.md) method to the Presentation API.
- Added the [ApiShape/GetGeometry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/GetGeometry.md) method to the Presentation API.
- Added the [ApiShape/SetGeometry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShape/Methods/SetGeometry.md) method to the Presentation API.
- Added the [GeometryFormulaType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/GeometryFormulaType.md) type to the simple type definitions.

### Path methods

- Added the [ApiPath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPath.md) class to the Document API.
- Added the [ApiPath/ArcTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPath/Methods/ArcTo.md) method to the Document API.
- Added the [ApiPath/CubicBezTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPath/Methods/CubicBezTo.md) method to the Document API.
- Added the [ApiPath/Close](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPath/Methods/Close.md) method to the Document API.
- Added the [ApiPath/GetCommand](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPath/Methods/GetCommand.md) method to the Document API.
- Added the [ApiPath/GetCommandCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPath/Methods/GetCommandCount.md) method to the Document API.
- Added the [ApiPath/GetCommands](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPath/Methods/GetCommands.md) method to the Document API.
- Added the [ApiPath/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPath/Methods/GetFill.md) method to the Document API.
- Added the [ApiPath/GetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPath/Methods/GetHeight.md) method to the Document API.
- Added the [ApiPath/GetStroke](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPath/Methods/GetStroke.md) method to the Document API.
- Added the [ApiPath/GetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPath/Methods/GetWidth.md) method to the Document API.
- Added the [ApiPath/LineTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPath/Methods/LineTo.md) method to the Document API.
- Added the [ApiPath/MoveTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPath/Methods/MoveTo.md) method to the Document API.
- Added the [ApiPath/QuadBezTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPath/Methods/QuadBezTo.md) method to the Document API.
- Added the [ApiPath/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPath/Methods/SetFill.md) method to the Document API.
- Added the [ApiPath/SetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPath/Methods/SetHeight.md) method to the Document API.
- Added the [ApiPath/SetStroke](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPath/Methods/SetStroke.md) method to the Document API.
- Added the [ApiPath/SetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPath/Methods/SetWidth.md) method to the Document API.
- Added the [ApiPath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath.md) class to the Spreadsheet API.
- Added the [ApiPath/ArcTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/ArcTo.md) method to the Spreadsheet API.
- Added the [ApiPath/CubicBezTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/CubicBezTo.md) method to the Spreadsheet API.
- Added the [ApiPath/Close](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPath/Methods/Close.md) method to the Spreadsheet API.
- Added the [ApiPath/GetCommand](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/GetCommand.md) method to the Spreadsheet API.
- Added the [ApiPath/GetCommandCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/GetCommandCount.md) method to the Spreadsheet API.
- Added the [ApiPath/GetCommands](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/GetCommands.md) method to the Spreadsheet API.
- Added the [ApiPath/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/GetFill.md) method to the Spreadsheet API.
- Added the [ApiPath/GetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/GetHeight.md) method to the Spreadsheet API.
- Added the [ApiPath/GetStroke](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/GetStroke.md) method to the Spreadsheet API.
- Added the [ApiPath/GetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/GetWidth.md) method to the Spreadsheet API.
- Added the [ApiPath/LineTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/LineTo.md) method to the Spreadsheet API.
- Added the [ApiPath/MoveTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/MoveTo.md) method to the Spreadsheet API.
- Added the [ApiPath/QuadBezTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/QuadBezTo.md) method to the Spreadsheet API.
- Added the [ApiPath/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/SetFill.md) method to the Spreadsheet API.
- Added the [ApiPath/SetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/SetHeight.md) method to the Spreadsheet API.
- Added the [ApiPath/SetStroke](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/SetStroke.md) method to the Spreadsheet API.
- Added the [ApiPath/SetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/SetWidth.md) method to the Spreadsheet API.
- Added the [ApiPath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPath.md) class to the Presentation API.
- Added the [ApiPath/ArcTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPath/Methods/ArcTo.md) method to the Presentation API.
- Added the [ApiPath/CubicBezTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPath/Methods/CubicBezTo.md) method to the Presentation API.
- Added the [ApiPath/Close](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPath/Methods/Close.md) method to the Presentation API.
- Added the [ApiPath/GetCommand](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPath/Methods/GetCommand.md) method to the Presentation API.
- Added the [ApiPath/GetCommandCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPath/Methods/GetCommandCount.md) method to the Presentation API.
- Added the [ApiPath/GetCommands](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPath/Methods/GetCommands.md) method to the Presentation API.
- Added the [ApiPath/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPath/Methods/GetFill.md) method to the Presentation API.
- Added the [ApiPath/GetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPath/Methods/GetHeight.md) method to the Presentation API.
- Added the [ApiPath/GetStroke](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPath/Methods/GetStroke.md) method to the Presentation API.
- Added the [ApiPath/GetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPath/Methods/GetWidth.md) method to the Presentation API.
- Added the [ApiPath/LineTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPath/Methods/LineTo.md) method to the Presentation API.
- Added the [ApiPath/MoveTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPath/Methods/MoveTo.md) method to the Presentation API.
- Added the [ApiPath/QuadBezTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPath/Methods/QuadBezTo.md) method to the Presentation API.
- Added the [ApiPath/SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPath/Methods/SetFill.md) method to the Presentation API.
- Added the [ApiPath/SetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPath/Methods/SetHeight.md) method to the Presentation API.
- Added the [ApiPath/SetStroke](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPath/Methods/SetStroke.md) method to the Presentation API.
- Added the [ApiPath/SetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPath/Methods/SetWidth.md) method to the Presentation API.
- Added the [PathFillType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/PathFillType.md) type to the simple type definitions.

### Path command methods

- Added the [ApiPathCommand](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPathCommand.md) class to the Document API.
- Added the [ApiPathCommand/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPathCommand/Methods/GetType.md) method to the Document API.
- Added the [ApiPathCommand/GetX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPathCommand/Methods/GetX.md) method to the Document API.
- Added the [ApiPathCommand/GetY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPathCommand/Methods/GetY.md) method to the Document API.
- Added the [ApiPathCommand/GetX0](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPathCommand/Methods/GetX0.md) method to the Document API.
- Added the [ApiPathCommand/GetY0](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPathCommand/Methods/GetY0.md) method to the Document API.
- Added the [ApiPathCommand/GetX1](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPathCommand/Methods/GetX1.md) method to the Document API.
- Added the [ApiPathCommand/GetY1](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPathCommand/Methods/GetY1.md) method to the Document API.
- Added the [ApiPathCommand/GetX2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPathCommand/Methods/GetX2.md) method to the Document API.
- Added the [ApiPathCommand/GetY2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPathCommand/Methods/GetY2.md) method to the Document API.
- Added the [ApiPathCommand/GetWR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPathCommand/Methods/GetWR.md) method to the Document API.
- Added the [ApiPathCommand/GetHR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPathCommand/Methods/GetHR.md) method to the Presentation API.
- Added the [ApiPathCommand/GetStartAngle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPathCommand/Methods/GetStartAngle.md) method to the Document API.
- Added the [ApiPathCommand/GetSweepAngle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPathCommand/Methods/GetSweepAngle.md) method to the Document API.
- Added the [ApiPathCommand](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPathCommand.md) class to the Spreadsheet API.
- Added the [ApiPathCommand/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPathCommand/Methods/GetType.md) method to the Spreadsheet API.
- Added the [ApiPathCommand/GetX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPathCommand/Methods/GetX.md) method to the Spreadsheet API.
- Added the [ApiPathCommand/GetY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPathCommand/Methods/GetY.md) method to the Spreadsheet API.
- Added the [ApiPathCommand/GetX0](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPathCommand/Methods/GetX0.md) method to the Spreadsheet API.
- Added the [ApiPathCommand/GetY0](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPathCommand/Methods/GetY0.md) method to the Spreadsheet API.
- Added the [ApiPathCommand/GetX1](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPathCommand/Methods/GetX1.md) method to the Spreadsheet API.
- Added the [ApiPathCommand/GetY1](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPathCommand/Methods/GetY1.md) method to the Spreadsheet API.
- Added the [ApiPathCommand/GetX2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPathCommand/Methods/GetX2.md) method to the Spreadsheet API.
- Added the [ApiPathCommand/GetY2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPathCommand/Methods/GetY2.md) method to the Spreadsheet API.
- Added the [ApiPathCommand/GetWR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPathCommand/Methods/GetWR.md) method to the Spreadsheet API.
- Added the [ApiPathCommand/GetHR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPathCommand/Methods/GetHR.md) method to the Spreadsheet API.
- Added the [ApiPathCommand/GetStartAngle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPathCommand/Methods/GetStartAngle.md) method to the Spreadsheet API.
- Added the [ApiPathCommand/GetSweepAngle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPathCommand/Methods/GetSweepAngle.md) method to the Spreadsheet API.
- Added the [ApiPathCommand](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPathCommand.md) class to the Presentation API.
- Added the [ApiPathCommand/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPathCommand/Methods/GetType.md) method to the Presentation API.
- Added the [ApiPathCommand/GetX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPathCommand/Methods/GetX.md) method to the Presentation API.
- Added the [ApiPathCommand/GetY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPathCommand/Methods/GetY.md) method to the Presentation API.
- Added the [ApiPathCommand/GetX0](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPathCommand/Methods/GetX0.md) method to the Presentation API.
- Added the [ApiPathCommand/GetY0](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPathCommand/Methods/GetY0.md) method to the Presentation API.
- Added the [ApiPathCommand/GetX1](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPathCommand/Methods/GetX1.md) method to the Presentation API.
- Added the [ApiPathCommand/GetY1](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPathCommand/Methods/GetY1.md) method to the Presentation API.
- Added the [ApiPathCommand/GetX2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPathCommand/Methods/GetX2.md) method to the Presentation API.
- Added the [ApiPathCommand/GetY2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPathCommand/Methods/GetY2.md) method to the Presentation API.
- Added the [ApiPathCommand/GetWR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPathCommand/Methods/GetWR.md) method to the Presentation API.
- Added the [ApiPathCommand/GetHR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPathCommand/Methods/GetHR.md) method to the Presentation API.
- Added the [ApiPathCommand/GetStartAngle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPathCommand/Methods/GetStartAngle.md) method to the Presentation API.
- Added the [ApiPathCommand/GetSweepAngle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPathCommand/Methods/GetSweepAngle.md) method to the Presentation API.
- Added the [PathCommandType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/PathCommandType.md) type to the simple type definitions.

### Custom XML methods

- Added the [ApiCustomXmlNode](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlNode.md) class to Spreadsheet API.
- Added the [ApiCustomXmlNode/Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlNode/Methods/Add.md) method to Spreadsheet API.
- Added the [ApiCustomXmlNode/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlNode/Methods/Delete.md) method to Spreadsheet API.
- Added the [ApiCustomXmlNode/DeleteAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlNode/Methods/DeleteAttribute.md) method to Spreadsheet API.
- Added the [ApiCustomXmlNode/GetAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlNode/Methods/GetAttribute.md) method to Spreadsheet API.
- Added the [ApiCustomXmlNode/GetAttributes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlNode/Methods/GetAttributes.md) method to Spreadsheet API.
- Added the [ApiCustomXmlNode/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlNode/Methods/GetClassType.md) method to Spreadsheet API.
- Added the [ApiCustomXmlNode/GetNodeName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlNode/Methods/GetNodeName.md) method to Spreadsheet API.
- Added the [ApiCustomXmlNode/GetNodes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlNode/Methods/GetNodes.md) method to Spreadsheet API.
- Added the [ApiCustomXmlNode/GetNodeValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlNode/Methods/GetNodeValue.md) method to Spreadsheet API.
- Added the [ApiCustomXmlNode/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlNode/Methods/GetParent.md) method to Spreadsheet API.
- Added the [ApiCustomXmlNode/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlNode/Methods/GetText.md) method to Spreadsheet API.
- Added the [ApiCustomXmlNode/GetXml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlNode/Methods/GetXml.md) method to Spreadsheet API.
- Added the [ApiCustomXmlNode/GetXPath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlNode/Methods/GetXPath.md) method to Spreadsheet API.
- Added the [ApiCustomXmlNode/SetAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlNode/Methods/SetAttribute.md) method to Spreadsheet API.
- Added the [ApiCustomXmlNode/SetNodeValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlNode/Methods/SetNodeValue.md) method to Spreadsheet API.
- Added the [ApiCustomXmlNode/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlNode/Methods/SetText.md) method to Spreadsheet API.
- Added the [ApiCustomXmlNode/SetXml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlNode/Methods/SetXml.md) method to Spreadsheet API.
- Added the [ApiCustomXmlNode/UpdateAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlNode/Methods/UpdateAttribute.md) method to Spreadsheet API.
- Added the [ApiCustomXmlPart](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlPart.md) class to Spreadsheet API.
- Added the [ApiCustomXmlPart/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlPart/Methods/Delete.md) method to Spreadsheet API.
- Added the [ApiCustomXmlPart/DeleteAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlPart/Methods/DeleteAttribute.md) method to Spreadsheet API.
- Added the [ApiCustomXmlPart/DeleteElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlPart/Methods/DeleteElement.md) method to Spreadsheet API.
- Added the [ApiCustomXmlPart/GetAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlPart/Methods/GetAttribute.md) method to Spreadsheet API.
- Added the [ApiCustomXmlPart/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlPart/Methods/GetClassType.md) method to Spreadsheet API.
- Added the [ApiCustomXmlPart/GetId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlPart/Methods/GetId.md) method to Spreadsheet API.
- Added the [ApiCustomXmlPart/GetNodes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlPart/Methods/GetNodes.md) method to Spreadsheet API.
- Added the [ApiCustomXmlPart/GetXml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlPart/Methods/GetXml.md) method to Spreadsheet API.
- Added the [ApiCustomXmlPart/InsertAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlPart/Methods/InsertAttribute.md) method to Spreadsheet API.
- Added the [ApiCustomXmlPart/InsertElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlPart/Methods/InsertElement.md) method to Spreadsheet API.
- Added the [ApiCustomXmlPart/UpdateAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlPart/Methods/UpdateAttribute.md) method to Spreadsheet API.
- Added the [ApiCustomXmlPart/UpdateElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlPart/Methods/UpdateElement.md) method to Spreadsheet API.
- Added the [ApiCustomXmlParts](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlParts.md) class to Spreadsheet API.
- Added the [ApiCustomXmlParts/Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlParts/Methods/Add.md) method to Spreadsheet API.
- Added the [ApiCustomXmlParts/GetAll](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlParts/Methods/GetAll.md) method to Spreadsheet API.
- Added the [ApiCustomXmlParts/GetById](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlParts/Methods/GetById.md) method to Spreadsheet API.
- Added the [ApiCustomXmlParts/GetByNamespace](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlParts/Methods/GetByNamespace.md) method to Spreadsheet API.
- Added the [ApiCustomXmlParts/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlParts/Methods/GetClassType.md) method to Spreadsheet API.
- Added the [ApiCustomXmlParts/GetCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomXmlParts/Methods/GetCount.md) method to Spreadsheet API.
- Added the [ApiWorksheet/GetCustomXmlParts](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/GetCustomXmlParts.md) method to Spreadsheet API.
- Added the [ApiCustomXmlNode](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlNode.md) class to Presentation API.
- Added the [ApiCustomXmlNode/Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlNode/Methods/Add.md) method to Presentation API.
- Added the [ApiCustomXmlNode/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlNode/Methods/Delete.md) method to Presentation API.
- Added the [ApiCustomXmlNode/DeleteAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlNode/Methods/DeleteAttribute.md) method to Presentation API.
- Added the [ApiCustomXmlNode/GetAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlNode/Methods/GetAttribute.md) method to Presentation API.
- Added the [ApiCustomXmlNode/GetAttributes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlNode/Methods/GetAttributes.md) method to Presentation API.
- Added the [ApiCustomXmlNode/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlNode/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiCustomXmlNode/GetNodeName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlNode/Methods/GetNodeName.md) method to Presentation API.
- Added the [ApiCustomXmlNode/GetNodes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlNode/Methods/GetNodes.md) method to Presentation API.
- Added the [ApiCustomXmlNode/GetNodeValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlNode/Methods/GetNodeValue.md) method to Presentation API.
- Added the [ApiCustomXmlNode/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlNode/Methods/GetParent.md) method to Presentation API.
- Added the [ApiCustomXmlNode/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlNode/Methods/GetText.md) method to Presentation API.
- Added the [ApiCustomXmlNode/GetXml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlNode/Methods/GetXml.md) method to Presentation API.
- Added the [ApiCustomXmlNode/GetXPath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlNode/Methods/GetXPath.md) method to Presentation API.
- Added the [ApiCustomXmlNode/SetAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlNode/Methods/SetAttribute.md) method to Presentation API.
- Added the [ApiCustomXmlNode/SetNodeValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlNode/Methods/SetNodeValue.md) method to Presentation API.
- Added the [ApiCustomXmlNode/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlNode/Methods/SetText.md) method to Presentation API.
- Added the [ApiCustomXmlNode/SetXml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlNode/Methods/SetXml.md) method to Presentation API.
- Added the [ApiCustomXmlNode/UpdateAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlNode/Methods/UpdateAttribute.md) method to Presentation API.
- Added the [ApiCustomXmlPart](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlPart.md) class to Presentation API.
- Added the [ApiCustomXmlPart/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlPart/Methods/Delete.md) method to Presentation API.
- Added the [ApiCustomXmlPart/DeleteAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlPart/Methods/DeleteAttribute.md) method to Presentation API.
- Added the [ApiCustomXmlPart/DeleteElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlPart/Methods/DeleteElement.md) method to Presentation API.
- Added the [ApiCustomXmlPart/GetAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlPart/Methods/GetAttribute.md) method to Presentation API.
- Added the [ApiCustomXmlPart/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlPart/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiCustomXmlPart/GetId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlPart/Methods/GetId.md) method to Presentation API.
- Added the [ApiCustomXmlPart/GetNodes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlPart/Methods/GetNodes.md) method to Presentation API.
- Added the [ApiCustomXmlPart/GetXml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlPart/Methods/GetXml.md) method to Presentation API.
- Added the [ApiCustomXmlPart/InsertAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlPart/Methods/InsertAttribute.md) method to Presentation API.
- Added the [ApiCustomXmlPart/InsertElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlPart/Methods/InsertElement.md) method to Presentation API.
- Added the [ApiCustomXmlPart/UpdateAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlPart/Methods/UpdateAttribute.md) method to Presentation API.
- Added the [ApiCustomXmlPart/UpdateElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlPart/Methods/UpdateElement.md) method to Presentation API.
- Added the [ApiCustomXmlParts](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlParts.md) class to Presentation API.
- Added the [ApiCustomXmlParts/Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlParts/Methods/Add.md) method to Presentation API.
- Added the [ApiCustomXmlParts/GetAll](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlParts/Methods/GetAll.md) method to Presentation API.
- Added the [ApiCustomXmlParts/GetById](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlParts/Methods/GetById.md) method to Presentation API.
- Added the [ApiCustomXmlParts/GetByNamespace](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlParts/Methods/GetByNamespace.md) method to Presentation API.
- Added the [ApiCustomXmlParts/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlParts/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiCustomXmlParts/GetCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomXmlParts/Methods/GetCount.md) method to Presentation API.
- Added the [ApiPresentation/GetCustomXmlParts](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetCustomXmlParts.md) method to Presentation API.

### Conversion methods

- Added the [Api/CentimetersToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CentimetersToPoints.md) method to the Document API.
- Added the [Api/EmusToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/EmusToPoints.md) method to the Document API.
- Added the [Api/InchesToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/InchesToPoints.md) method to the Document API.
- Added the [Api/LinesToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/LinesToPoints.md) method to the Document API.
- Added the [Api/MillimetersToPixels](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/MillimetersToPixels.md) method to the Document API.
- Added the [Api/MillimetersToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/MillimetersToPoints.md) method to the Document API.
- Added the [Api/PicasToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/PicasToPoints.md) method to the Document API.
- Added the [Api/PixelsToEmus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/PixelsToEmus.md) method to the Document API.
- Added the [Api/PixelsToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/PixelsToPoints.md) method to the Document API.
- Added the [Api/PointsToCentimeters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/PointsToCentimeters.md) method to the Document API.
- Added the [Api/PointsToEmus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/PointsToEmus.md) method to the Document API.
- Added the [Api/PointsToInches](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/PointsToInches.md) method to the Document API.
- Added the [Api/PointsToLines](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/PointsToLines.md) method to the Document API.
- Added the [Api/PointsToMillimeters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/PointsToMillimeters.md) method to the Document API.
- Added the [Api/PointsToPicas](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/PointsToPicas.md) method to the Document API.
- Added the [Api/PointsToPixels](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/PointsToPixels.md) method to the Document API.
- Added the [Api/PointsToTwips](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/PointsToTwips.md) method to the Document API.
- Added the [Api/TwipsToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/TwipsToPoints.md) method to the Document API.
- Added the [Api/CentimetersToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/CentimetersToPoints.md) method to the Spreadsheet API.
- Added the [Api/EmusToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/EmusToPoints.md) method to the Spreadsheet API.
- Added the [Api/InchesToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/InchesToPoints.md) method to the Spreadsheet API.
- Added the [Api/LinesToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/LinesToPoints.md) method to the Spreadsheet API.
- Added the [Api/MillimetersToPixels](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/MillimetersToPixels.md) method to the Spreadsheet API.
- Added the [Api/MillimetersToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/MillimetersToPoints.md) method to the Spreadsheet API.
- Added the [Api/PicasToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/PicasToPoints.md) method to the Spreadsheet API.
- Added the [Api/PixelsToEmus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/PixelsToEmus.md) method to the Spreadsheet API.
- Added the [Api/PixelsToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/PixelsToPoints.md) method to the Spreadsheet API.
- Added the [Api/PointsToCentimeters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/PointsToCentimeters.md) method to the Spreadsheet API.
- Added the [Api/PointsToEmus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/PointsToEmus.md) method to the Spreadsheet API.
- Added the [Api/PointsToInches](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/PointsToInches.md) method to the Spreadsheet API.
- Added the [Api/PointsToLines](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/PointsToLines.md) method to the Spreadsheet API.
- Added the [Api/PointsToMillimeters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/PointsToMillimeters.md) method to the Spreadsheet API.
- Added the [Api/PointsToPicas](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/PointsToPicas.md) method to the Spreadsheet API.
- Added the [Api/PointsToPixels](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/PointsToPixels.md) method to the Spreadsheet API.
- Added the [Api/PointsToTwips](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/PointsToTwips.md) method to the Spreadsheet API.
- Added the [Api/TwipsToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/TwipsToPoints.md) method to the Spreadsheet API.
- Added the [Api/CentimetersToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CentimetersToPoints.md) method to the Presentation API.
- Added the [Api/EmusToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/EmusToPoints.md) method to the Presentation API.
- Added the [Api/InchesToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/InchesToPoints.md) method to the Presentation API.
- Added the [Api/LinesToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/LinesToPoints.md) method to the Presentation API.
- Added the [Api/MillimetersToPixels](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/MillimetersToPixels.md) method to the Presentation API.
- Added the [Api/MillimetersToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/MillimetersToPoints.md) method to the Presentation API.
- Added the [Api/PicasToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/PicasToPoints.md) method to the Presentation API.
- Added the [Api/PixelsToEmus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/PixelsToEmus.md) method to the Presentation API.
- Added the [Api/PixelsToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/PixelsToPoints.md) method to the Presentation API.
- Added the [Api/PointsToCentimeters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/PointsToCentimeters.md) method to the Presentation API.
- Added the [Api/PointsToEmus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/PointsToEmus.md) method to the Presentation API.
- Added the [Api/PointsToInches](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/PointsToInches.md) method to the Presentation API.
- Added the [Api/PointsToLines](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/PointsToLines.md) method to the Presentation API.
- Added the [Api/PointsToMillimeters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/PointsToMillimeters.md) method to the Presentation API.
- Added the [Api/PointsToPicas](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/PointsToPicas.md) method to the Presentation API.
- Added the [Api/PointsToPixels](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/PointsToPixels.md) method to the Presentation API.
- Added the [Api/PointsToTwips](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/PointsToTwips.md) method to the Presentation API.
- Added the [Api/TwipsToPoints](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/TwipsToPoints.md) method to the Presentation API.

### Methods for managing properties

- Added the [Api/CreateParaPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateParaPr.md) method to the Document API.
- Added the [Api/CreateTableCellPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateTableCellPr.md) method to the Document API.
- Added the [Api/CreateTablePr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateTablePr.md) method to the Document API.
- Added the [Api/CreateTableRowPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateTableRowPr.md) method to the Document API.
- Added the [Api/CreateTableStylePr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateTableStylePr.md) method to the Document API.
- Added the [ApiStyle/SetConditionalTableStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiStyle/Methods/SetConditionalTableStyle.md) method to the Document API.
- Added the [ApiStyle/SetParaPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiStyle/Methods/SetParaPr.md) method to the Document API.
- Added the [ApiStyle/SetTableCellPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiStyle/Methods/SetTableCellPr.md) method to the Document API.
- Added the [ApiStyle/SetTablePr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiStyle/Methods/SetTablePr.md) method to the Document API.
- Added the [ApiStyle/SetTableRowPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiStyle/Methods/SetTableRowPr.md) method to the Document API.
- Added the [ApiStyle/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiStyle/Methods/SetTextPr.md) method to the Document API.
- Added the [ApiTableStylePr/SetParaPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableStylePr/Methods/SetParaPr.md) method to the Document API.
- Added the [ApiTableStylePr/SetTableCellPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableStylePr/Methods/SetTableCellPr.md) method to the Document API.
- Added the [ApiTableStylePr/SetTablePr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableStylePr/Methods/SetTablePr.md) method to the Document API.
- Added the [ApiTableStylePr/SetTableRowPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableStylePr/Methods/SetTableRowPr.md) method to the Document API.
- Added the [ApiTableStylePr/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableStylePr/Methods/SetTextPr.md) method to the Document API.

### Section methods

- Added the [ApiSection/GetFooterDistance](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSection/Methods/GetFooterDistance.md) method to the Document API.
- Added the [ApiSection/GetHeaderDistance](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSection/Methods/GetHeaderDistance.md) method to the Document API.
- Added the [ApiSection/GetPageMarginBottom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSection/Methods/GetPageMarginBottom.md) method to the Document API.
- Added the [ApiSection/GetPageMarginLeft](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSection/Methods/GetPageMarginLeft.md) method to the Document API.
- Added the [ApiSection/GetPageMarginRight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSection/Methods/GetPageMarginRight.md) method to the Document API.
- Added the [ApiSection/GetPageMarginTop](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSection/Methods/GetPageMarginTop.md) method to the Document API.

### Workbook methods

- Added the [ApiWorkbook/GetActiveChart](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/GetActiveChart.md) method to the Spreadsheet API.
- Added the [ApiWorkbook/GetActiveSheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/GetActiveSheet.md) method to the Spreadsheet API.
- Added the [ApiWorkbook/GetAllPivotTables](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/GetAllPivotTables.md) method to the Spreadsheet API.
- Added the [ApiWorkbook/GetCustomProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/GetCustomProperties.md) method to the Spreadsheet API.
- Added the [ApiWorkbook/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/GetName.md) method to the Spreadsheet API.
- Added the [ApiWorkbook/GetSheets](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/GetSheets.md) method to the Spreadsheet API.
- Added the [ApiWorkbook/GetTheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/GetTheme.md) method to the Spreadsheet API.
- Added the [ApiWorkbook/Save](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/Save.md) method to the Spreadsheet API.

### Pivot tables methods

- Added the [ApiPivotField/AutoSort](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/AutoSort.md) method to the Spreadsheet API.
- Added the [ApiPivotField/GetPivotFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetPivotFilters.md) method to the Spreadsheet API.
- Added the [ApiPivotFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotFilters.md) class to the Spreadsheet API.
- Added the [ApiPivotFilters/Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotFilters/Methods/Add.md) method to the Spreadsheet API.
- Added the [ApiPivotItem/GetVisible](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotItem/Methods/GetVisible.md) method to the Spreadsheet API.
- Added the [ApiPivotItem/SetVisible](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotItem/Methods/SetVisible.md) method to the Spreadsheet API.
- Added the `AutoSortField` property to the [ApiPivotField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField.md) object of Spreadsheet API.
- Added the `AutoSortOrder` property to the [ApiPivotField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField.md) object of Spreadsheet API.
- Added the `PivotFilters` property to the [ApiPivotField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField.md) object of Spreadsheet API.
- Added the `Visible` property to the [ApiPivotItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotItem.md) object of Spreadsheet API.
- Added the [XlPivotFilterType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlPivotFilterType.md) type to the simple type definitions.

### Range methods

- Added the [ApiRange/ClearContents](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/ClearContents.md) method to the Spreadsheet API.
- Added the [ApiRange/ClearFormats](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/ClearFormats.md) method to the Spreadsheet API.
- Added the [ApiRange/ClearHyperlinks](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/ClearHyperlinks.md) method to the Spreadsheet API.
- Added the [ApiRange/GetCellsCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/GetCellsCount.md) method to the Spreadsheet API.
- Added the [ApiRange/GetColumnsCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/GetColumnsCount.md) method to the Spreadsheet API.
- Added the [ApiRange/GetCurrentRegion](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/GetCurrentRegion.md) method to the Spreadsheet API.
- Added the [ApiRange/GetEntireColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/GetEntireColumn.md) method to the Spreadsheet API.
- Added the [ApiRange/GetEntireRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/GetEntireRow.md) method to the Spreadsheet API.
- Added the [ApiRange/GetRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/GetRange.md) method to the Spreadsheet API.
- Added the [ApiRange/GetRowsCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/GetRowsCount.md) method to the Spreadsheet API.
- Added the [ApiRange/Offset](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/Offset.md) method to the Spreadsheet API.
- Added the [ApiRange/Resize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/Resize.md) method to the Spreadsheet API.
- Added the [ApiRange/SetReadingOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/SetReadingOrder.md) method to the Spreadsheet API.
- Added the `CellsCount` property to the [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) object of Spreadsheet API.
- Added the `ColumnsCount` property to the [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) object of Spreadsheet API.
- Added the `CurrentRegion` property to the [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) object of Spreadsheet API.
- Added the `EntireColumn` property to the [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) object of Spreadsheet API.
- Added the `EntireRow` property to the [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) object of Spreadsheet API.
- Added the `RowsCount` property to the [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) object of Spreadsheet API.

### Presentation methods

- Added the [ApiLayout/GetAllTables](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/GetAllTables.md) method to the Presentation API.
- Added the [ApiMaster/GetAllTables](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/GetAllTables.md) method to the Presentation API.
- Added the [ApiNotesPage/GetBodyShapeText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiNotesPage/Methods/GetBodyShapeText.md) method to the Presentation API.
- Added the [ApiPresentation/GetAllTables](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetAllTables.md) method to the Presentation API.
- Added the [ApiSlide/GetAllTables](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/GetAllTables.md) method to the Presentation API.

### Other methods

- Added the [ApiDocument/GetDocumentVisitor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetDocumentVisitor.md) method to the Document API.
- Added the [ApiDocument/GoToPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GoToPage.md) method to the Document API.
- Added the [ApiDocumentContent/GetDocumentVisitor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/GetDocumentVisitor.md) method to the Document API.
- Added the [ApiParagraph/SetReadingOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/SetReadingOrder.md) method to the Document API.
- Added the [ApiDrawing/Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/Select.md) method to the Spreadsheet API.
- Added the [ApiTheme/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTheme/Methods/GetClassType.md) method to the Spreadsheet API.
- Added the [ApiTheme/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTheme/Methods/GetName.md) method to the Spreadsheet API.
- Added the [ApiFormBase/GetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormBase/Methods/GetPlaceholderText.md) method to Form API.
- Added the [ReadingOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ReadingOrder.md) type to the simple type definitions.
- Added the [XlPivotFilterType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlPivotFilterType.md) type to the simple type definitions.

## Version 9.0

### Content control methods

- Added the [Api/CreateCheckBoxContentControl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateCheckBoxContentControl.md) method to Document API.
- Added the [Api/CreateComboBoxContentControl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateComboBoxContentControl.md) method to Document API.
- Added the [Api/CreateDatePickerContentControl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateDatePickerContentControl.md) method to Document API.
- Added the [Api/CreateDropDownListContentControl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateDropDownListContentControl.md) method to Document API.
- Added the [Api/CreatePictureContentControl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreatePictureContentControl.md) method to Document API.
- Added the [ApiBlockLvlSdt/GetAppearance](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/GetAppearance.md) method to Document API.
- Added the [ApiBlockLvlSdt/GetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/GetBackgroundColor.md) method to Document API.
- Added the [ApiBlockLvlSdt/GetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/GetBorderColor.md) method to Document API.
- Added the [ApiBlockLvlSdt/GetDataBinding](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/GetDataBinding.md) method to Document API.
- Added the [ApiBlockLvlSdt/GetDataForXmlMapping](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/GetDataForXmlMapping.md) method to Document API.
- Added the [ApiBlockLvlSdt/GetId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/GetId.md) method to Document API.
- Added the [ApiBlockLvlSdt/IsPicture](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/IsPicture.md) method to Document API.
- Added the [ApiBlockLvlSdt/SetAppearance](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/SetAppearance.md) method to Document API.
- Added the [ApiBlockLvlSdt/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/SetBackgroundColor.md) method to Document API.
- Added the [ApiBlockLvlSdt/SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/SetBorderColor.md) method to Document API.
- Added the [ApiBlockLvlSdt/SetDataBinding](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/SetDataBinding.md) method to Document API.
- Added the [ApiBlockLvlSdt/SetId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/SetId.md) method to Document API.
- Added the [ApiBlockLvlSdt/SetPicture](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/SetPicture.md) method to Document API.
- Added the [ApiBlockLvlSdt/UpdateFromXmlMapping](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/UpdateFromXmlMapping.md) method to Document API.
- Added the [ApiDocument/AddCheckBoxContentControl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/AddCheckBoxContentControl.md) method to Document API.
- Added the [ApiDocument/AddComboBoxContentControl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/AddComboBoxContentControl.md) method to Document API.
- Added the [ApiDocument/AddDatePickerContentControl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/AddDatePickerContentControl.md) method to Document API.
- Added the [ApiDocument/AddDropDownListContentControl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/AddDropDownListContentControl.md) method to Document API.
- Added the [ApiDocument/AddPictureContentControl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/AddPictureContentControl.md) method to Document API.
- Added the [ApiDocumentContent/GetCurrentContentControl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/GetCurrentContentControl.md) method to Document API.
- Added the [ApiInlineLvlSdt/AddListItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/AddListItem.md) method to Document API.
- Added the [ApiInlineLvlSdt/GetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/GetBackgroundColor.md) method to Document API.
- Added the [ApiInlineLvlSdt/GetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/GetBorderColor.md) method to Document API.
- Added the [ApiInlineLvlSdt/GetDataBinding](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/GetDataBinding.md) method to Document API.
- Added the [ApiInlineLvlSdt/GetDataForXmlMapping](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/GetDataForXmlMapping.md) method to Document API.
- Added the [ApiInlineLvlSdt/GetDate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/GetDate.md) method to Document API.
- Added the [ApiInlineLvlSdt/GetId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/GetId.md) method to Document API.
- Added the [ApiInlineLvlSdt/IsCheckBox](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/IsCheckBox.md) method to Document API.
- Added the [ApiInlineLvlSdt/IsCheckBoxChecked](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/IsCheckBoxChecked.md) method to Document API.
- Added the [ApiInlineLvlSdt/IsComboBox](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/IsComboBox.md) method to Document API.
- Added the [ApiInlineLvlSdt/IsDatePicker](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/IsDatePicker.md) method to Document API.
- Added the [ApiInlineLvlSdt/IsDropDownList](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/IsDropDownList.md) method to Document API.
- Added the [ApiInlineLvlSdt/IsPicture](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/IsPicture.md) method to Document API.
- Added the [ApiInlineLvlSdt/RemoveListItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/RemoveListItem.md) method to Document API.
- Added the [ApiInlineLvlSdt/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/SetBackgroundColor.md) method to Document API.
- Added the [ApiInlineLvlSdt/SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/SetBorderColor.md) method to Document API.
- Added the [ApiInlineLvlSdt/SetCheckBoxChecked](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/SetCheckBoxChecked.md) method to Document API.
- Added the [ApiInlineLvlSdt/SetDate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/SetDate.md) method to Document API.
- Added the [ApiInlineLvlSdt/SetDateFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/SetDateFormat.md) method to Document API.
- Added the [ApiInlineLvlSdt/SetPicture](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/SetPicture.md) method to Document API.
- Added the [ApiInlineLvlSdt/SetPictureSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/SetPictureSize.md) method to Document API.
- Added the [ApiInlineLvlSdt/Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/Select.md) method to Document API.
- Added the [ApiInlineLvlSdt/SelectListItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/SelectListItem.md) method to Document API.
- Added the [ApiInlineLvlSdt/SetDataBinding](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/SetDataBinding.md) method to Document API.
- Added the [ApiInlineLvlSdt/SetId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/SetId.md) method to Document API.
- Added the [ApiInlineLvlSdt/UpdateFromXmlMapping](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/UpdateFromXmlMapping.md) method to Document API.
- Added the [ContentControlCheckBoxPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ContentControlCheckBoxPr.md) type to the simple type definitions.
- Added the [ContentControlDatePr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ContentControlDatePr.md) type to the simple type definitions.
- Added the [ContentControlListItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ContentControlListItem.md) type to the simple type definitions.

### Custom XML methods

- Added the [ApiCustomXmlNode](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlNode.md) class to Document API.
- Added the [ApiCustomXmlNode/Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlNode/Methods/Add.md) method to Document API.
- Added the [ApiCustomXmlNode/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlNode/Methods/Delete.md) method to Document API.
- Added the [ApiCustomXmlNode/DeleteAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlNode/Methods/DeleteAttribute.md) method to Document API.
- Added the [ApiCustomXmlNode/GetAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlNode/Methods/GetAttribute.md) method to Document API.
- Added the [ApiCustomXmlNode/GetAttributes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlNode/Methods/GetAttributes.md) method to Document API.
- Added the [ApiCustomXmlNode/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlNode/Methods/GetClassType.md) method to Document API.
- Added the [ApiCustomXmlNode/GetNodeName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlNode/Methods/GetNodeName.md) method to Document API.
- Added the [ApiCustomXmlNode/GetNodes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlNode/Methods/GetNodes.md) method to Document API.
- Added the [ApiCustomXmlNode/GetNodeValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlNode/Methods/GetNodeValue.md) method to Document API.
- Added the [ApiCustomXmlNode/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlNode/Methods/GetParent.md) method to Document API.
- Added the [ApiCustomXmlNode/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlNode/Methods/GetText.md) method to Document API.
- Added the [ApiCustomXmlNode/GetXml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlNode/Methods/GetXml.md) method to Document API.
- Added the [ApiCustomXmlNode/GetXPath](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlNode/Methods/GetXPath.md) method to Document API.
- Added the [ApiCustomXmlNode/SetAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlNode/Methods/SetAttribute.md) method to Document API.
- Added the [ApiCustomXmlNode/SetNodeValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlNode/Methods/SetNodeValue.md) method to Document API.
- Added the [ApiCustomXmlNode/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlNode/Methods/SetText.md) method to Document API.
- Added the [ApiCustomXmlNode/SetXml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlNode/Methods/SetXml.md) method to Document API.
- Added the [ApiCustomXmlNode/UpdateAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlNode/Methods/UpdateAttribute.md) method to Document API.
- Added the [ApiCustomXmlPart](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlPart.md) class to Document API.
- Added the [ApiCustomXmlPart/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlPart/Methods/Delete.md) method to Document API.
- Added the [ApiCustomXmlPart/DeleteAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlPart/Methods/DeleteAttribute.md) method to Document API.
- Added the [ApiCustomXmlPart/DeleteElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlPart/Methods/DeleteElement.md) method to Document API.
- Added the [ApiCustomXmlPart/GetAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlPart/Methods/GetAttribute.md) method to Document API.
- Added the [ApiCustomXmlPart/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlPart/Methods/GetClassType.md) method to Document API.
- Added the [ApiCustomXmlPart/GetId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlPart/Methods/GetId.md) method to Document API.
- Added the [ApiCustomXmlPart/GetNodes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlPart/Methods/GetNodes.md) method to Document API.
- Added the [ApiCustomXmlPart/GetXml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlPart/Methods/GetXml.md) method to Document API.
- Added the [ApiCustomXmlPart/InsertAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlPart/Methods/InsertAttribute.md) method to Document API.
- Added the [ApiCustomXmlPart/InsertElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlPart/Methods/InsertElement.md) method to Document API.
- Added the [ApiCustomXmlPart/UpdateAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlPart/Methods/UpdateAttribute.md) method to Document API.
- Added the [ApiCustomXmlPart/UpdateElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlPart/Methods/UpdateElement.md) method to Document API.
- Added the [ApiCustomXmlParts](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlParts.md) class to Document API.
- Added the [ApiCustomXmlParts/Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlParts/Methods/Add.md) method to Document API.
- Added the [ApiCustomXmlParts/GetAll](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlParts/Methods/GetAll.md) method to Document API.
- Added the [ApiCustomXmlParts/GetById](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlParts/Methods/GetById.md) method to Document API.
- Added the [ApiCustomXmlParts/GetByNamespace](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlParts/Methods/GetByNamespace.md) method to Document API.
- Added the [ApiCustomXmlParts/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlParts/Methods/GetClassType.md) method to Document API.
- Added the [ApiCustomXmlParts/GetCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomXmlParts/Methods/GetCount.md) method to Document API.
- Added the [ApiDocument/GetCustomXmlParts](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetCustomXmlParts.md) method to Document API.
- Added the [CustomXmlNodeAttribute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/CustomXmlNodeAttribute.md) type to the simple type definitions.
- Added the [XmlMapping](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/XmlMapping.md) type to the simple type definitions.

### Form methods

- Added the [ApiCheckBoxForm/GetChoiceName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/GetChoiceName.md) method to Document API.
- Added the [ApiCheckBoxForm/SetChoiceName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/SetChoiceName.md) method to Document API.
- Added the [ApiComplexForm/Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/Add.md) method to Document API.
- Added the [ApiComplexForm/ClearContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/ClearContent.md) method to Document API.
- Added the [ApiComplexForm/GetSubForms](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm/Methods/GetSubForms.md) method to Document API.
- Added the [ApiDateForm/GetDate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/GetDate.md) method to Document API.
- Added the [ApiDateForm/SetDate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/SetDate.md) method to Document API.
- Added the [ApiDocument/GetFormsByKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetFormsByKey.md) method to Document API.
- Added the [ApiDocument/GetFormsByRole](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetFormsByRole.md) method to Document API.
- Added the [ApiDocument/GetFormKeysByRole](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetFormKeysByRole.md) method to Document API.
- Added the [ApiDocument/GetFormValueByKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetFormValueByKey.md) method to Document API.
- Added the [ApiFormBase/GetRole](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetRole.md) method to Document API.
- Added the [ApiFormBase/GetTag](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetTag.md) method to Document API.
- Added the [ApiFormBase/SetRole](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetRole.md) method to Document API.
- Added the [ApiFormBase/SetTag](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetTag.md) method to Document API.
- Added the [Api/CreateComplexForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Api/Methods/CreateComplexForm.md) method to Form API.
- Added the [ApiDocument/GetFormRoles](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDocument/Methods/GetFormRoles.md) method to Form API.
- Added the [ApiFormRoles](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormRoles.md) class to Form API.
- Added the [ApiFormRoles/Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormRoles/Methods/Add.md) method to Form API.
- Added the [ApiFormRoles/GetAllRoles](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormRoles/Methods/GetAllRoles.md) method to Form API.
- Added the [ApiFormRoles/GetCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormRoles/Methods/GetCount.md) method to Form API.
- Added the [ApiFormRoles/GetRoleColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormRoles/Methods/GetRoleColor.md) method to Form API.
- Added the [ApiFormRoles/HaveRole](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormRoles/Methods/HaveRole.md) method to Form API.
- Added the [ApiFormRoles/MoveDown](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormRoles/Methods/MoveDown.md) method to Form API.
- Added the [ApiFormRoles/MoveUp](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormRoles/Methods/MoveUp.md) method to Form API.
- Added the [ApiFormRoles/Remove](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormRoles/Methods/Remove.md) method to Form API.
- Added the [ApiFormRoles/SetRoleColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormRoles/Methods/SetRoleColor.md) method to Form API.
- Added the `role` property to the [FormPrBase](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/FormPrBase.md) object.
- Added the [DateFormPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/DateFormPr.md) type to the simple type definitions.
- Added the [RoleProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/RoleProperties.md) type to the simple type definitions.

### Custom properties methods

- Added the [ApiCustomProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomProperties.md) class to Document API.
- Added the [ApiDocument/GetCustomProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetCustomProperties.md) method to Document API.
- Added the [ApiCustomProperties/Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomProperties/Methods/Add.md) method to Document API.
- Added the [ApiCustomProperties/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomProperties/Methods/GetClassType.md) method to Document API.
- Added the [ApiCustomProperties/Get](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCustomProperties/Methods/Get.md) method to Document API.
- Added the [Api/GetCustomProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/GetCustomProperties.md) method to Spreadsheet API.
- Added the [ApiCustomProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomProperties.md) class to Spreadsheet API.
- Added the [ApiCustomProperties/Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomProperties/Methods/Add.md) method to Spreadsheet API.
- Added the [ApiCustomProperties/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomProperties/Methods/GetClassType.md) method to Spreadsheet API.
- Added the [ApiCustomProperties/Get](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomProperties/Methods/Get.md) method to Spreadsheet API.
- Added the [ApiCustomProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomProperties.md) class to Presentation API.
- Added the [ApiCustomProperties/Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomProperties/Methods/Add.md) method to Presentation API.
- Added the [ApiCustomProperties/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomProperties/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiCustomProperties/Get](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCustomProperties/Methods/Get.md) method to Presentation API.
- Added the [ApiPresentation/GetCustomProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetCustomProperties.md) method to Presentation API.

### Core methods

- Added the [ApiCore](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore.md) class to Document API.
- Added the [ApiCore/GetCategory](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/GetCategory.md) method to Document API.
- Added the [ApiCore/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/GetClassType.md) method to Document API.
- Added the [ApiCore/GetContentStatus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/GetContentStatus.md) method to Document API.
- Added the [ApiCore/GetCreated](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/GetCreated.md) method to Document API.
- Added the [ApiCore/GetCreator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/GetCreator.md) method to Document API.
- Added the [ApiCore/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/GetDescription.md) method to Document API.
- Added the [ApiCore/GetIdentifier](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/GetIdentifier.md) method to Document API.
- Added the [ApiCore/GetKeywords](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/GetKeywords.md) method to Document API.
- Added the [ApiCore/GetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/GetLanguage.md) method to Document API.
- Added the [ApiCore/GetLastModifiedBy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/GetLastModifiedBy.md) method to Document API.
- Added the [ApiCore/GetLastPrinted](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/GetLastPrinted.md) method to Document API.
- Added the [ApiCore/GetModified](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/GetModified.md) method to Document API.
- Added the [ApiCore/GetRevision](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/GetRevision.md) method to Document API.
- Added the [ApiCore/GetSubject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/GetSubject.md) method to Document API.
- Added the [ApiCore/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/GetTitle.md) method to Document API.
- Added the [ApiCore/GetVersion](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/GetVersion.md) method to Document API.
- Added the [ApiCore/SetCategory](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/SetCategory.md) method to Document API.
- Added the [ApiCore/SetContentStatus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/SetContentStatus.md) method to Document API.
- Added the [ApiCore/SetCreated](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/SetCreated.md) method to Document API.
- Added the [ApiCore/SetCreator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/SetCreator.md) method to Document API.
- Added the [ApiCore/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/SetDescription.md) method to Document API.
- Added the [ApiCore/SetIdentifier](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/SetIdentifier.md) method to Document API.
- Added the [ApiCore/SetKeywords](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/SetKeywords.md) method to Document API.
- Added the [ApiCore/SetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/SetLanguage.md) method to Document API.
- Added the [ApiCore/SetLastModifiedBy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/SetLastModifiedBy.md) method to Document API.
- Added the [ApiCore/SetLastPrinted](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/SetLastPrinted.md) method to Document API.
- Added the [ApiCore/SetModified](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/SetModified.md) method to Document API.
- Added the [ApiCore/SetRevision](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/SetRevision.md) method to Document API.
- Added the [ApiCore/SetSubject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/SetSubject.md) method to Document API.
- Added the [ApiCore/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/SetTitle.md) method to Document API.
- Added the [ApiCore/SetVersion](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCore/Methods/SetVersion.md) method to Document API.
- Added the [ApiDocument/GetCore](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetCore.md) method to Document API.
- Added the [Api/GetCore](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/GetCore.md) method to Spreadsheet API.
- Added the [ApiCore](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore.md) class to Spreadsheet API.
- Added the [ApiCore/GetCategory](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/GetCategory.md) method to Spreadsheet API.
- Added the [ApiCore/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/GetClassType.md) method to Spreadsheet API.
- Added the [ApiCore/GetContentStatus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/GetContentStatus.md) method to Spreadsheet API.
- Added the [ApiCore/GetCreated](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/GetCreated.md) method to Spreadsheet API.
- Added the [ApiCore/GetCreator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/GetCreator.md) method to Spreadsheet API.
- Added the [ApiCore/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/GetDescription.md) method to Spreadsheet API.
- Added the [ApiCore/GetIdentifier](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/GetIdentifier.md) method to Spreadsheet API.
- Added the [ApiCore/GetKeywords](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/GetKeywords.md) method to Spreadsheet API.
- Added the [ApiCore/GetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/GetLanguage.md) method to Spreadsheet API.
- Added the [ApiCore/GetLastModifiedBy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/GetLastModifiedBy.md) method to Spreadsheet API.
- Added the [ApiCore/GetLastPrinted](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/GetLastPrinted.md) method to Spreadsheet API.
- Added the [ApiCore/GetModified](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/GetModified.md) method to Spreadsheet API.
- Added the [ApiCore/GetRevision](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/GetRevision.md) method to Spreadsheet API.
- Added the [ApiCore/GetSubject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/GetSubject.md) method to Spreadsheet API.
- Added the [ApiCore/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/GetTitle.md) method to Spreadsheet API.
- Added the [ApiCore/GetVersion](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/GetVersion.md) method to Spreadsheet API.
- Added the [ApiCore/SetCategory](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/SetCategory.md) method to Spreadsheet API.
- Added the [ApiCore/SetContentStatus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/SetContentStatus.md) method to Spreadsheet API.
- Added the [ApiCore/SetCreated](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/SetCreated.md) method to Spreadsheet API.
- Added the [ApiCore/SetCreator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/SetCreator.md) method to Spreadsheet API.
- Added the [ApiCore/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/SetDescription.md) method to Spreadsheet API.
- Added the [ApiCore/SetIdentifier](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/SetIdentifier.md) method to Spreadsheet API.
- Added the [ApiCore/SetKeywords](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/SetKeywords.md) method to Spreadsheet API.
- Added the [ApiCore/SetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/SetLanguage.md) method to Spreadsheet API.
- Added the [ApiCore/SetLastModifiedBy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/SetLastModifiedBy.md) method to Spreadsheet API.
- Added the [ApiCore/SetLastPrinted](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/SetLastPrinted.md) method to Spreadsheet API.
- Added the [ApiCore/SetModified](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/SetModified.md) method to Spreadsheet API.
- Added the [ApiCore/SetRevision](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/SetRevision.md) method to Spreadsheet API.
- Added the [ApiCore/SetSubject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/SetSubject.md) method to Spreadsheet API.
- Added the [ApiCore/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/SetTitle.md) method to Spreadsheet API.
- Added the [ApiCore/SetVersion](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCore/Methods/SetVersion.md) method to Spreadsheet API.
- Added the [ApiCore](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore.md) class to Presentation API.
- Added the [ApiCore/GetCategory](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/GetCategory.md) method to Presentation API.
- Added the [ApiCore/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiCore/GetContentStatus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/GetContentStatus.md) method to Presentation API.
- Added the [ApiCore/GetCreated](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/GetCreated.md) method to Presentation API.
- Added the [ApiCore/GetCreator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/GetCreator.md) method to Presentation API.
- Added the [ApiCore/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/GetDescription.md) method to Presentation API.
- Added the [ApiCore/GetIdentifier](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/GetIdentifier.md) method to Presentation API.
- Added the [ApiCore/GetKeywords](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/GetKeywords.md) method to Presentation API.
- Added the [ApiCore/GetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/GetLanguage.md) method to Presentation API.
- Added the [ApiCore/GetLastModifiedBy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/GetLastModifiedBy.md) method to Presentation API.
- Added the [ApiCore/GetLastPrinted](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/GetLastPrinted.md) method to Presentation API.
- Added the [ApiCore/GetModified](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/GetModified.md) method to Presentation API.
- Added the [ApiCore/GetRevision](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/GetRevision.md) method to Presentation API.
- Added the [ApiCore/GetSubject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/GetSubject.md) method to Presentation API.
- Added the [ApiCore/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/GetTitle.md) method to Presentation API.
- Added the [ApiCore/GetVersion](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/GetVersion.md) method to Presentation API.
- Added the [ApiCore/SetCategory](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/SetCategory.md) method to Presentation API.
- Added the [ApiCore/SetContentStatus](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/SetContentStatus.md) method to Presentation API.
- Added the [ApiCore/SetCreated](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/SetCreated.md) method to Presentation API.
- Added the [ApiCore/SetCreator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/SetCreator.md) method to Presentation API.
- Added the [ApiCore/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/SetDescription.md) method to Presentation API.
- Added the [ApiCore/SetIdentifier](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/SetIdentifier.md) method to Presentation API.
- Added the [ApiCore/SetKeywords](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/SetKeywords.md) method to Presentation API.
- Added the [ApiCore/SetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/SetLanguage.md) method to Presentation API.
- Added the [ApiCore/SetLastModifiedBy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/SetLastModifiedBy.md) method to Presentation API.
- Added the [ApiCore/SetLastPrinted](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/SetLastPrinted.md) method to Presentation API.
- Added the [ApiCore/SetModified](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/SetModified.md) method to Presentation API.
- Added the [ApiCore/SetRevision](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/SetRevision.md) method to Presentation API.
- Added the [ApiCore/SetSubject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/SetSubject.md) method to Presentation API.
- Added the [ApiCore/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/SetTitle.md) method to Presentation API.
- Added the [ApiCore/SetVersion](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiCore/Methods/SetVersion.md) method to Presentation API.
- Added the [ApiPresentation/GetCore](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetCore.md) method to Presentation API.

### Range methods

- Added the [ApiRange/AddField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/AddField.md) method to Document API.
- Added the [ApiRange/MoveCursorToPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/MoveCursorToPos.md) method to Document API.
- Added the [ApiRange/GetFormulaArray](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/GetFormulaArray.md) method to Spreadsheet API.
- Added the [ApiRange/SetFormulaArray](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/SetFormulaArray.md) method to Spreadsheet API.

### Document methods

- Added the [ApiDocument/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetInternalId.md) method to Document API.
- Added the [ApiDocument/InsertBlankPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/InsertBlankPage.md) method to Document API.
- Added the [ApiDocument/MoveCursorToEnd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/MoveCursorToEnd.md) method to Document API.
- Added the [ApiDocument/MoveCursorToStart](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/MoveCursorToStart.md) method to Document API.
- Added the [ApiDocument/SetAssistantTrackRevisions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/SetAssistantTrackRevisions.md) method to Document API.
- Added the [ApiDocumentContent/GetCurrentParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/GetCurrentParagraph.md) method to Document API.
- Added the [ApiDocumentContent/GetCurrentRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/GetCurrentRun.md) method to Document API.
- Added the [ApiDocumentContent/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/GetInternalId.md) method to Document API.
- Added the [ApiDocumentContent/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDocumentContent/Methods/GetInternalId.md) method to Spreadsheet API.
- Added the [ApiDocumentContent/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDocumentContent/Methods/GetInternalId.md) method to Presentation API.

### Drawing methods

- Added the [ApiDrawing/GetRotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/GetRotation.md) method to Document API.
- Added the [ApiDrawing/SetRotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/SetRotation.md) method to Document API.
- Added the [ApiDrawing/GetRotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/GetRotation.md) method to Spreadsheet API.
- Added the [ApiDrawing/SetRotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/SetRotation.md) method to Spreadsheet API.
- Added the [ApiDrawing/GetRotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/GetRotation.md) method to Presentation API.
- Added the [ApiDrawing/SetRotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/SetRotation.md) method to Presentation API.

### Comment methods

- Added the [ApiDocument/ShowComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/ShowComment.md) method to Document API.
- Added the [ApiComment/GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiComment/Methods/GetPosition.md) method to Presentation API.
- Added the [ApiComment/SetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiComment/Methods/SetPosition.md) method to Presentation API.
- Added the `posX` and `posY` parameters to the [ApiSlide/AddComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/AddComment.md) method of Presentation API.

### Presentation methods

- Added the [ApiPresentation/AddMathEquation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/AddMathEquation.md) method to Presentation API.
- Added the [ApiPresentation/GetAllCharts](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetAllCharts.md) method to Presentation API.
- Added the [ApiPresentation/GetAllDrawings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetAllDrawings.md) method to Presentation API.
- Added the [ApiPresentation/GetAllImages](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetAllImages.md) method to Presentation API.
- Added the [ApiPresentation/GetAllOleObjects](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetAllOleObjects.md) method to Presentation API.
- Added the [ApiPresentation/GetAllShapes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetAllShapes.md) method to Presentation API.
- Added the `nIndex` parameter to the [ApiPresentation/AddSlide](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/AddSlide.md) method of Presentation API.

### Layout methods

- Added the [ApiLayout/GetLayoutType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/GetLayoutType.md) method to Presentation API.
- Added the [ApiMaster/GetAllLayouts](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/GetAllLayouts.md) method to Presentation API.
- Added the [ApiMaster/GetLayoutByType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/GetLayoutByType.md) method to Presentation API.
- Added the [LayoutType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/LayoutType.md) type to the simple type definitions.

### Notes page methods

- Added the [ApiNotesPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiNotesPage.md) class to Presentation API.
- Added the [ApiNotesPage/AddBodyShapeText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiNotesPage/Methods/AddBodyShapeText.md) method to Presentation API.
- Added the [ApiNotesPage/GetBodyShape](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiNotesPage/Methods/GetBodyShape.md) method to Presentation API.
- Added the [ApiNotesPage/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiNotesPage/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiSlide/AddNotesText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/AddNotesText.md) method to Presentation API.
- Added the [ApiSlide/GetNotesPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/GetNotesPage.md) method to Presentation API.

### Other methods

- Added the [Api/GetByInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/GetByInternalId.md) method to Document API.
- Added the [ApiRun/GetParentParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun/Methods/GetParentParagraph.md) method to Document API.
- Added the [ApiTablePr/SetTableBorderAll](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTablePr/Methods/SetTableBorderAll.md) method to Document API.
- Added the `fontSlot` parameter to the [ApiTextPr/GetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetFontFamily.md) method of Document API.
- Added the [ApiParagraph/Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/Select.md) method to Presentation API.
- Added the [ApiSlide/AddComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/AddComment.md) method to Presentation API.
- Added the [Base64Img](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/Base64Img.md) type to the simple type definitions.


## Version 8.3

### Bookmark methods

- Added the [ApiBookmark](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBookmark.md) class to Document API.
- Added the [ApiBookmark/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBookmark/Methods/Delete.md) method to Document API.
- Added the [ApiBookmark/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBookmark/Methods/GetName.md) method to Document API.
- Added the [ApiBookmark/GetRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBookmark/Methods/GetRange.md) method to Document API.
- Added the [ApiBookmark/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBookmark/Methods/GetText.md) method to Document API.
- Added the [ApiBookmark/GoTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBookmark/Methods/GoTo.md) method to Document API.
- Added the [ApiBookmark/Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBookmark/Methods/Select.md) method to Document API.
- Added the [ApiBookmark/SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBookmark/Methods/SetName.md) method to Document API.
- Added the [ApiBookmark/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBookmark/Methods/SetText.md) method to Document API.
- Added the [ApiDocument/GetBookmark](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetBookmark.md) method to Document API.

### Group methods

- Added the [Api/CreateGroup](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateGroup.md) method to Document API.
- Added the [ApiDocument/GroupDrawings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GroupDrawings.md) method to Document API.
- Added the [ApiGroup](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGroup.md) class to Document API.
- Added the [ApiGroup/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGroup/Methods/GetClassType.md) method to Document API.
- Added the [ApiGroup/Ungroup](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGroup/Methods/Ungroup.md) method to Document API.
- Added the [ApiDrawing/GetParentSheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/GetParentSheet.md) method to Spreadsheet API.
- Added the [Api/CreateGroup](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateGroup.md) method to Presentation API.
- Added the [ApiGroup](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGroup.md) class to Presentation API.
- Added the [ApiGroup/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiGroup/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiLayout/GroupDrawings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/GroupDrawings.md) method to Presentation API.
- Added the [ApiMaster/GroupDrawings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/GroupDrawings.md) method to Presentation API.
- Added the [ApiSlide/GroupDrawings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/GroupDrawings.md) method to Presentation API.
- Added the [Drawing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/Drawing.md) type to the simple type definitions.
- Added the [DrawingForGroup](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/DrawingForGroup.md) type to the simple type definitions.

### Content control methods

- Added the [ApiBlockLvlSdt/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/Copy.md) method to Document API.
- Added the [ApiBlockLvlSdt/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/GetInternalId.md) method to Document API.
- Added the [ApiInlineLvlSdt/GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/GetInternalId.md) method to Document API.

### Document methods

- Added the [ApiDocument/GetCurrentPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetCurrentPage.md) method to Document API.
- Added the [ApiDocument/GetCurrentVisiblePages](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetCurrentVisiblePages.md) method to Document API.
- Added the [ApiDocumentContent/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/GetText.md) method to Document API.

### Section methods

- Added the [ApiSection/GetStartPageNumber](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSection/Methods/GetStartPageNumber.md) method to Document API.
- Added the [ApiSection/SetStartPageNumber](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSection/Methods/SetStartPageNumber.md) method to Document API.

### Autofilter methods

- Added the [ApiRange/SetAutoFilter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/SetAutoFilter.md) method to Spreadsheet API.
- Added the [XlAutoFilterOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlAutoFilterOperator.md) type to the simple type definitions.
- Added the [XlDynamicFilterCriteria](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlDynamicFilterCriteria.md) type to the simple type definitions.

### Selection methods

- Added the [Api/GetSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/GetSelection.md) method to Presentation API.
- Added the [ApiSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSelection.md) class to Presentation API.
- Added the [ApiSelection/GetShapes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSelection/Methods/GetShapes.md) method to Presentation API.
- Added the [ApiSelection/GetSlides](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSelection/Methods/GetSlides.md) method to Presentation API.
- Added the [ApiSelection/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSelection/Methods/GetType.md) method to Presentation API.
- Added the [ApiSelection/IsEmpty](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSelection/Methods/IsEmpty.md) method to Presentation API.
- Added the [SelectionType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/SelectionType.md) type to the simple type definitions.

### Slide methods

- Added the [ApiPresentation/GetAllSlideMasters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetAllSlideMasters.md) method to Presentation API.
- Added the [ApiPresentation/GetAllSlides](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetAllSlides.md) method to Presentation API.
- Added the [ApiSlide/Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/Select.md) method to Presentation API.

### Other methods

- Added the [ApiNumberingLevel/LinkWithStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiNumberingLevel/Methods/LinkWithStyle.md) method to Document API.
- Moved the [GetContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/GetContent.md) method of Document API from the `ApiShape` class to the `ApiDrawing` class.
- Added the [ApiLayout/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/GetName.md) method to Presentation API.
- Added the `keepPosition` parameter to the [ApiFormBase/ToFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormBase/Methods/ToFixed.md) method of Form API.
- Added the [PivotTableFieldOptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/PivotTableFieldOptions.md) type to the simple type definitions.
- Added the [PivotTableFilterAreaInfo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/PivotTableFilterAreaInfo.md) type to the simple type definitions.

## Version 8.2

### Range methods

- Added the [ApiRange/GetEndPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/GetEndPage.md) method to Document API.
- Added the [ApiRange/GetStartPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/GetStartPage.md) method to Document API.
- Added the [ApiRange/GetEndPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/GetEndPos.md) method to Document API.
- Added the [ApiRange/GetStartPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/GetStartPos.md) method to Document API.
- Added the [ApiRange/GetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/GetTextPr.md) method to Document API.
- Added the [ApiRange/SetEndPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/SetEndPos.md) method to Document API.
- Added the [ApiRange/SetStartPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/SetStartPos.md) method to Document API.

### Document methods

- Added the [ApiDocument/AddComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/AddComment.md) method to Document API.
- Added the [ApiDocument/AddMathEquation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/AddMathEquation.md) method to Document API.
- Added the [ApiDocument/GetCurrentSentence](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetCurrentSentence.md) method to Document API.
- Added the [ApiDocument/GetCurrentWord](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetCurrentWord.md) method to Document API.
- Added the [ApiDocument/ReplaceCurrentSentence](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/ReplaceCurrentSentence.md) method to Document API.
- Added the [ApiDocument/ReplaceCurrentWord](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/ReplaceCurrentWord.md) method to Document API.
- Added the [ApiDocument/SelectCurrentWord](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/SelectCurrentWord.md) method to Document API.
- Added the [ApiDocument/UpdateAllFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/UpdateAllFields.md) method to Document API.

### Pivot tables methods

- Added the [Api/GetAllPivotTables](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/GetAllPivotTables.md) method to Spreadsheet API.
- Added the [Api/GetPivotByName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/GetPivotByName.md) method to Spreadsheet API.
- Added the [Api/InsertPivotExistingWorksheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/InsertPivotExistingWorksheet.md) method to Spreadsheet API.
- Added the [Api/InsertPivotNewWorksheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/InsertPivotNewWorksheet.md) method to Spreadsheet API.
- Added the [Api/RefreshAllPivots](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/RefreshAllPivots.md) method to Spreadsheet API.
- Added the [ApiPivotDataField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField.md) class to Spreadsheet API.
- Added the [ApiPivotDataField/ClearAllFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/ClearAllFilters.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/ClearLabelFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/ClearLabelFilters.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/ClearManualFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/ClearManualFilters.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/ClearValueFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/ClearValueFilters.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetCaption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetCaption.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetCurrentPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetCurrentPage.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetDragToColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetDragToColumn.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetDragToData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetDragToData.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetDragToPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetDragToPage.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetDragToRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetDragToRow.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetFunction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetFunction.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetIndex.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetLayoutBlankLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetLayoutBlankLine.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetLayoutCompactRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetLayoutCompactRow.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetLayoutForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetLayoutForm.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetLayoutPageBreak](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetLayoutPageBreak.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetLayoutSubtotalLocation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetLayoutSubtotalLocation.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetLayoutSubtotals](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetLayoutSubtotals.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetName.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetNumberFormat.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetOrientation.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetParent.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetPivotField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetPivotField.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetPivotItems](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetPivotItems.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetPosition.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetRepeatLabels](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetRepeatLabels.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetShowAllItems](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetShowAllItems.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetShowingInAxis](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetShowingInAxis.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetSourceName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetSourceName.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetSubtotalName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetSubtotalName.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetSubtotals](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetSubtotals.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetTable.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/GetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/GetValue.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/Move](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/Move.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/Remove](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/Remove.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetCaption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetCaption.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetDragToColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetDragToColumn.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetDragToData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetDragToData.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetDragToPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetDragToPage.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetDragToRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetDragToRow.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetFunction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetFunction.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetLayoutBlankLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetLayoutBlankLine.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetLayoutCompactRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetLayoutCompactRow.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetLayoutForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetLayoutForm.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetLayoutPageBreak](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetLayoutPageBreak.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetLayoutSubtotalLocation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetLayoutSubtotalLocation.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetLayoutSubtotals](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetLayoutSubtotals.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetName.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetNumberFormat.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetOrientation.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetPosition.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetRepeatLabels](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetRepeatLabels.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetShowAllItems](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetShowAllItems.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetSubtotalName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetSubtotalName.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetSubtotals](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetSubtotals.md) method to Spreadsheet API.
- Added the [ApiPivotDataField/SetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotDataField/Methods/SetValue.md) method to Spreadsheet API.
- Added the [ApiPivotField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField.md) class to Spreadsheet API.
- Added the [ApiPivotField/ClearAllFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/ClearAllFilters.md) method to Spreadsheet API.
- Added the [ApiPivotField/ClearLabelFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/ClearLabelFilters.md) method to Spreadsheet API.
- Added the [ApiPivotField/ClearManualFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/ClearManualFilters.md) method to Spreadsheet API.
- Added the [ApiPivotField/ClearValueFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/ClearValueFilters.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetCaption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetCaption.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetCurrentPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetCurrentPage.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetDragToColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetDragToColumn.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetDragToData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetDragToData.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetDragToPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetDragToPage.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetDragToRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetDragToRow.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetIndex.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetLayoutBlankLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetLayoutBlankLine.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetLayoutCompactRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetLayoutCompactRow.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetLayoutForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetLayoutForm.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetLayoutPageBreak](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetLayoutPageBreak.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetLayoutSubtotalLocation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetLayoutSubtotalLocation.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetLayoutSubtotals](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetLayoutSubtotals.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetName.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetOrientation.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetParent.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetPivotItems](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetPivotItems.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetPosition.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetRepeatLabels](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetRepeatLabels.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetShowAllItems](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetShowAllItems.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetShowingInAxis](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetShowingInAxis.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetSourceName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetSourceName.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetSubtotalName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetSubtotalName.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetSubtotals](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetSubtotals.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetTable.md) method to Spreadsheet API.
- Added the [ApiPivotField/GetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetValue.md) method to Spreadsheet API.
- Added the [ApiPivotField/Move](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/Move.md) method to Spreadsheet API.
- Added the [ApiPivotField/Remove](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/Remove.md) method to Spreadsheet API.
- Added the [ApiPivotField/SetCaption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetCaption.md) method to Spreadsheet API.
- Added the [ApiPivotField/SetDragToColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetDragToColumn.md) method to Spreadsheet API.
- Added the [ApiPivotField/SetDragToData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetDragToData.md) method to Spreadsheet API.
- Added the [ApiPivotField/SetDragToPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetDragToPage.md) method to Spreadsheet API.
- Added the [ApiPivotField/SetDragToRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetDragToRow.md) method to Spreadsheet API.
- Added the [ApiPivotField/SetLayoutBlankLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetLayoutBlankLine.md) method to Spreadsheet API.
- Added the [ApiPivotField/SetLayoutCompactRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetLayoutCompactRow.md) method to Spreadsheet API.
- Added the [ApiPivotField/SetLayoutForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetLayoutForm.md) method to Spreadsheet API.
- Added the [ApiPivotField/SetLayoutPageBreak](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetLayoutPageBreak.md) method to Spreadsheet API.
- Added the [ApiPivotField/SetLayoutSubtotalLocation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetLayoutSubtotalLocation.md) method to Spreadsheet API.
- Added the [ApiPivotField/SetLayoutSubtotals](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetLayoutSubtotals.md) method to Spreadsheet API.
- Added the [ApiPivotField/SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetName.md) method to Spreadsheet API.
- Added the [ApiPivotField/SetOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetOrientation.md) method to Spreadsheet API.
- Added the [ApiPivotField/SetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetPosition.md) method to Spreadsheet API.
- Added the [ApiPivotField/SetRepeatLabels](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetRepeatLabels.md) method to Spreadsheet API.
- Added the [ApiPivotField/SetShowAllItems](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetShowAllItems.md) method to Spreadsheet API.
- Added the [ApiPivotField/SetSubtotalName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetSubtotalName.md) method to Spreadsheet API.
- Added the [ApiPivotField/SetSubtotals](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetSubtotals.md) method to Spreadsheet API.
- Added the [ApiPivotField/SetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetValue.md) method to Spreadsheet API.
- Added the [ApiPivotItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotItem.md) class to Spreadsheet API.
- Added the [ApiPivotItem/GetCaption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotItem/Methods/GetCaption.md) method to Spreadsheet API.
- Added the [ApiPivotItem/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotItem/Methods/GetName.md) method to Spreadsheet API.
- Added the [ApiPivotItem/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotItem/Methods/GetParent.md) method to Spreadsheet API.
- Added the [ApiPivotItem/GetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotItem/Methods/GetValue.md) method to Spreadsheet API.
- Added the [ApiPivotTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable.md) class to Spreadsheet API.
- Added the [ApiPivotTable/AddDataField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/AddDataField.md) method to Spreadsheet API.
- Added the [ApiPivotTable/AddFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/AddFields.md) method to Spreadsheet API.
- Added the [ApiPivotTable/ClearAllFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/ClearAllFilters.md) method to Spreadsheet API.
- Added the [ApiPivotTable/ClearTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/ClearTable.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetColumnFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetColumnFields.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetColumnGrand](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetColumnGrand.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetColumnRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetColumnRange.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetData.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetDataBodyRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetDataBodyRange.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetDataFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetDataFields.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetDescription.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetDisplayFieldCaptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetDisplayFieldCaptions.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetDisplayFieldsInReportFilterArea](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetDisplayFieldsInReportFilterArea.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetGrandTotalName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetGrandTotalName.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetHiddenFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetHiddenFields.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetName.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetPageFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetPageFields.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetParent.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetPivotData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetPivotData.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetPivotFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetPivotFields.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetRowFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetRowFields.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetRowGrand](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetRowGrand.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetRowRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetRowRange.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetSource](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetSource.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetStyleName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetStyleName.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetTableRange1](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetTableRange1.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetTableRange2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetTableRange2.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetTableStyleColumnHeaders](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetTableStyleColumnHeaders.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetTableStyleColumnStripes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetTableStyleColumnStripes.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetTableStyleRowHeaders](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetTableStyleRowHeaders.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetTableStyleRowStripes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetTableStyleRowStripes.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetTitle.md) method to Spreadsheet API.
- Added the [ApiPivotTable/GetVisibleFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/GetVisibleFields.md) method to Spreadsheet API.
- Added the [ApiPivotTable/MoveField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/MoveField.md) method to Spreadsheet API.
- Added the [ApiPivotTable/PivotValueCell](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/PivotValueCell.md) method to Spreadsheet API.
- Added the [ApiPivotTable/RefreshTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/RefreshTable.md) method to Spreadsheet API.
- Added the [ApiPivotTable/RemoveField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/RemoveField.md) method to Spreadsheet API.
- Added the [ApiPivotTable/Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/Select.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetColumnGrand](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetColumnGrand.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetDescription.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetDisplayFieldCaptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetDisplayFieldCaptions.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetDisplayFieldsInReportFilterArea](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetDisplayFieldsInReportFilterArea.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetGrandTotalName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetGrandTotalName.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetLayoutBlankLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetLayoutBlankLine.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetLayoutSubtotals](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetLayoutSubtotals.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetName.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetRepeatAllLabels](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetRepeatAllLabels.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetRowAxisLayout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetRowAxisLayout.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetRowGrand](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetRowGrand.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetSource](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetSource.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetStyleName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetStyleName.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetSubtotalLocation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetSubtotalLocation.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetTableStyleColumnHeaders](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetTableStyleColumnHeaders.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetTableStyleColumnStripes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetTableStyleColumnStripes.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetTableStyleRowHeaders](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetTableStyleRowHeaders.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetTableStyleRowStripes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetTableStyleRowStripes.md) method to Spreadsheet API.
- Added the [ApiPivotTable/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/SetTitle.md) method to Spreadsheet API.
- Added the [ApiPivotTable/ShowDetails](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/ShowDetails.md) method to Spreadsheet API.
- Added the [ApiPivotTable/Update](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable/Methods/Update.md) method to Spreadsheet API.
- Added the [ApiRange/GetPivotTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/GetPivotTable.md) method to Spreadsheet API.
- Added the [ApiWorksheet/GetAllPivotTables](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/GetAllPivotTables.md) method to Spreadsheet API.
- Added the [ApiWorksheet/GetPivotByName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/GetPivotByName.md) method to Spreadsheet API.
- Added the [ApiWorksheet/RefreshAllPivots](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/RefreshAllPivots.md) method to Spreadsheet API.
- Added the `PivotTable` property to the [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) object of Spreadsheet API.
- Added the `PivotTables` property to the [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api.md) object of Spreadsheet API.
- Added the `PivotTables` property to the [ApiWorksheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet.md) object of Spreadsheet API.
- Added the [DataConsolidateFunctionType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/DataConsolidateFunctionType.md) type to the simple type definitions.
- Added the [FieldsInReportFilterType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/FieldsInReportFilterType.md) type to the simple type definitions.
- Added the [LayoutSubtotalLocationType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/LayoutSubtotalLocationType.md) type to the simple type definitions.
- Added the [PivotFieldOrientationType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/PivotFieldOrientationType.md) type to the simple type definitions.
- Added the [PivotFieldSubtotals](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/PivotFieldSubtotals.md) type to the simple type definitions.
- Added the [PivotLayoutType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/PivotLayoutType.md) type to the simple type definitions.
- Added the [PivotMoveFieldType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/PivotMoveFieldType.md) type to the simple type definitions.

### Placeholder methods

- Added the [ApiLayout/GetDrawingsByPlaceholderType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/GetDrawingsByPlaceholderType.md) method to Presentation API.
- Added the [ApiMaster/GetDrawingsByPlaceholderType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/GetDrawingsByPlaceholderType.md) method to Presentation API.
- Added the [ApiPlaceholder/GetIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPlaceholder/Methods/GetIndex.md) method to Presentation API.
- Added the [ApiPlaceholder/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPlaceholder/Methods/GetType.md) method to Presentation API.
- Added the [ApiPlaceholder/SetIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPlaceholder/Methods/SetIndex.md) method to Presentation API.
- Added the [ApiSlide/GetDrawingsByPlaceholderType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/GetDrawingsByPlaceholderType.md) method to Presentation API.
- Added the [PlaceholderType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/PlaceholderType.md) type to the simple type definitions.

### Other methods

- Added the [ApiBlockLvlSdt/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/Copy.md) method to Document API.
- Added the [ApiParaPr/GetOutlineLvl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/GetOutlineLvl.md) method to Document API.
- Added the [ApiParaPr/SetOutlineLvl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/SetOutlineLvl.md) method to Document API.
- Added the [ApiRun/MoveCursorToPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun/Methods/MoveCursorToPos.md) method to Document API.
- Added the [ApiSection/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSection/Methods/GetType.md) method to Document API.
- Added the [Api/AddCustomFunctionLibrary](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/AddCustomFunctionLibrary.md) method to Spreadsheet API.
- Added the [ApiParaPr/GetOutlineLvl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParaPr/Methods/GetOutlineLvl.md) method to Spreadsheet API.
- Added the [ApiParaPr/SetOutlineLvl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiParaPr/Methods/SetOutlineLvl.md) method to Spreadsheet API.
- Added the [ApiDrawing/Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/Select.md) method to Presentation API.
- Added the [ApiParaPr/GetOutlineLvl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParaPr/Methods/GetOutlineLvl.md) method to Presentation API.
- Added the [ApiParaPr/SetOutlineLvl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParaPr/Methods/SetOutlineLvl.md) method to Presentation API.
- Added the `tag` property to the [FormPrBase](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/FormPrBase.md) object.
- Added the `ReviewedElement` property to the [ReviewReportRecord](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ReviewReportRecord.md) object.
- Added the [DeleteShiftDirection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/DeleteShiftDirection.md) type to the simple type definitions.
- Added the [Drawing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/Drawing.md) type to the simple type definitions.

## Version 8.1

### Date form methods

- Added the [ApiDateForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm.md) class to Document API.
- Added the [Api/CreateDateForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Api/Methods/CreateDateForm.md) method to Form API.
- Added the [ApiDateForm/Clear](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/Clear.md) method to Document API.
- Added the [ApiDateForm/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/Copy.md) method to Document API.
- Added the [ApiDateForm/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/GetClassType.md) method to Document API.
- Added the [ApiDateForm/GetFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/GetFormat.md) method to Document API.
- Added the [ApiDateForm/GetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/GetFormKey.md) method to Document API.
- Added the [ApiDateForm/GetFormType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/GetFormType.md) method to Document API.
- Added the [ApiDateForm/GetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/GetLanguage.md) method to Document API.
- Added the [ApiDateForm/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/GetText.md) method to Document API.
- Added the [ApiDateForm/GetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/GetTextPr.md) method to Document API.
- Added the [ApiDateForm/GetTime](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/GetTime.md) method to Document API.
- Added the [ApiDateForm/GetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/GetTipText.md) method to Document API.
- Added the [ApiDateForm/GetWrapperShape](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/GetWrapperShape.md) method to Document API.
- Added the [ApiDateForm/IsFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/IsFixed.md) method to Document API.
- Added the [ApiDateForm/IsRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/IsRequired.md) method to Document API.
- Added the [ApiDateForm/MoveCursorOutside](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/MoveCursorOutside.md) method to Document API.
- Added the [ApiDateForm/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/SetBackgroundColor.md) method to Document API.
- Added the [ApiDateForm/SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/SetBorderColor.md) method to Document API.
- Added the [ApiDateForm/SetFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/SetFormat.md) method to Document API.
- Added the [ApiDateForm/SetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/SetFormKey.md) method to Document API.
- Added the [ApiDateForm/SetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/SetLanguage.md) method to Document API.
- Added the [ApiDateForm/SetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/SetPlaceholderText.md) method to Document API.
- Added the [ApiDateForm/SetRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/SetRequired.md) method to Document API.
- Added the [ApiDateForm/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/SetTextPr.md) method to Document API.
- Added the [ApiDateForm/SetTime](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/SetTime.md) method to Document API.
- Added the [ApiDateForm/SetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/SetTipText.md) method to Document API.
- Added the [ApiDateForm/ToFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/ToFixed.md) method to Document API.
- Added the [ApiDateForm/ToInline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm/Methods/ToInline.md) method to Document API.
- Added the [DateFormPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/DateFormPr.md) type to the simple type definitions.
- Added the [DateFormPrBase](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/DateFormPrBase.md) type to the simple type definitions.

### Methods for setting text properties

- Added the [ApiTextPr/GetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetBold.md) method to Document API.
- Added the [ApiTextPr/GetCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetCaps.md) method to Document API.
- Added the [ApiTextPr/GetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetColor.md) method to Document API.
- Added the [ApiTextPr/GetDoubleStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetDoubleStrikeout.md) method to Document API.
- Added the [ApiTextPr/GetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetFontFamily.md) method to Document API.
- Added the [ApiTextPr/GetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetFontSize.md) method to Document API.
- Added the [ApiTextPr/GetHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetHighlight.md) method to Document API.
- Added the [ApiTextPr/GetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetItalic.md) method to Document API.
- Added the [ApiTextPr/GetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetLanguage.md) method to Document API.
- Added the [ApiTextPr/GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetPosition.md) method to Document API.
- Added the [ApiTextPr/GetShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetShd.md) method to Document API.
- Added the [ApiTextPr/GetSmallCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetSmallCaps.md) method to Document API.
- Added the [ApiTextPr/GetSpacing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetSpacing.md) method to Document API.
- Added the [ApiTextPr/GetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetStrikeout.md) method to Document API.
- Added the [ApiTextPr/GetStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetStyle.md) method to Document API.
- Added the [ApiTextPr/GetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetUnderline.md) method to Document API.
- Added the [ApiTextPr/GetVertAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/GetVertAlign.md) method to Document API.
- Added the [ApiTextPr/GetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextPr/Methods/GetBold.md) method to Spreadsheet API.
- Added the [ApiTextPr/GetCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextPr/Methods/GetCaps.md) method to Spreadsheet API.
- Added the [ApiTextPr/GetDoubleStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextPr/Methods/GetDoubleStrikeout.md) method to Spreadsheet API.
- Added the [ApiTextPr/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextPr/Methods/GetFill.md) method to Spreadsheet API.
- Added the [ApiTextPr/GetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextPr/Methods/GetFontFamily.md) method to Spreadsheet API.
- Added the [ApiTextPr/GetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextPr/Methods/GetFontSize.md) method to Spreadsheet API.
- Added the [ApiTextPr/GetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextPr/Methods/GetItalic.md) method to Spreadsheet API.
- Added the [ApiTextPr/GetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextPr/Methods/GetOutLine.md) method to Spreadsheet API.
- Added the [ApiTextPr/GetSmallCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextPr/Methods/GetSmallCaps.md) method to Spreadsheet API.
- Added the [ApiTextPr/GetSpacing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextPr/Methods/GetSpacing.md) method to Spreadsheet API.
- Added the [ApiTextPr/GetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextPr/Methods/GetStrikeout.md) method to Spreadsheet API.
- Added the [ApiTextPr/GetTextFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextPr/Methods/GetTextFill.md) method to Spreadsheet API.
- Added the [ApiTextPr/GetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextPr/Methods/GetUnderline.md) method to Spreadsheet API.
- Added the [ApiTextPr/GetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextPr/Methods/GetBold.md) method to Presentation API.
- Added the [ApiTextPr/GetCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextPr/Methods/GetCaps.md) method to Presentation API.
- Added the [ApiTextPr/GetDoubleStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextPr/Methods/GetDoubleStrikeout.md) method to Presentation API.
- Added the [ApiTextPr/GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextPr/Methods/GetFill.md) method to Presentation API.
- Added the [ApiTextPr/GetFontFamily](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextPr/Methods/GetFontFamily.md) method to Presentation API.
- Added the [ApiTextPr/GetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextPr/Methods/GetFontSize.md) method to Presentation API.
- Added the [ApiTextPr/GetHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextPr/Methods/GetHighlight.md) method to Presentation API.
- Added the [ApiTextPr/GetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextPr/Methods/GetItalic.md) method to Presentation API.
- Added the [ApiTextPr/GetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextPr/Methods/GetOutLine.md) method to Presentation API.
- Added the [ApiTextPr/GetSmallCaps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextPr/Methods/GetSmallCaps.md) method to Presentation API.
- Added the [ApiTextPr/GetSpacing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextPr/Methods/GetSpacing.md) method to Presentation API.
- Added the [ApiTextPr/GetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextPr/Methods/GetStrikeout.md) method to Presentation API.
- Added the [ApiTextPr/GetTextFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextPr/Methods/GetTextFill.md) method to Presentation API.
- Added the [ApiTextPr/GetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextPr/Methods/GetUnderline.md) method to Presentation API.

### Worksheet function methods

- Added the [ApiWorksheetFunction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction.md) class to Spreadsheet API.
- Added the [Api/GetWorksheetFunction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/GetWorksheetFunction.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ABS](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ABS.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ACCRINT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ACCRINT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ACCRINTM](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ACCRINTM.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ACOS](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ACOS.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ACOSH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ACOSH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ACOT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ACOT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ACOTH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ACOTH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/AGGREGATE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/AGGREGATE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/AMORDEGRC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/AMORDEGRC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/AMORLINC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/AMORLINC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/AND](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/AND.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ARABIC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ARABIC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ASC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ASC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ASIN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ASIN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ASINH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ASINH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ATAN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ATAN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ATAN2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ATAN2.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ATANH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ATANH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/AVEDEV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/AVEDEV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/AVERAGE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/AVERAGE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/AVERAGEA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/AVERAGEA.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/AVERAGEIF](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/AVERAGEIF.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/AVERAGEIFS](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/AVERAGEIFS.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BASE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BASE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BESSELI](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BESSELI.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BESSELJ](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BESSELJ.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BESSELK](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BESSELK.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BESSELY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BESSELY.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BETA_DIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BETA_DIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BETA_INV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BETA_INV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BETADIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BETADIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BETAINV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BETAINV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BIN2DEC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BIN2DEC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BIN2HEX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BIN2HEX.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BIN2OCT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BIN2OCT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BINOM_DIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BINOM_DIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BINOM_DIST_RANGE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BINOM_DIST_RANGE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BINOM_INV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BINOM_INV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BINOMDIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BINOMDIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BITAND](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BITAND.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BITLSHIFT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BITLSHIFT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BITOR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BITOR.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BITRSHIFT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BITRSHIFT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/BITXOR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/BITXOR.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CEILING](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CEILING.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CEILING_MATH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CEILING_MATH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CEILING_PRECISE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CEILING_PRECISE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CHAR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CHAR.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CHISQ_DIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CHISQ_DIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CHISQ_DIST_RT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CHISQ_DIST_RT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CHISQ_INV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CHISQ_INV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CHISQ_INV_RT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CHISQ_INV_RT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CHIDIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CHIDIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CHIINV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CHIINV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CHOOSE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CHOOSE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CLEAN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CLEAN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CODE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CODE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/COLUMNS](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/COLUMNS.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/COMBIN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/COMBIN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/COMBINA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/COMBINA.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/COMPLEX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/COMPLEX.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CONCATENATE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CONCATENATE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CONFIDENCE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CONFIDENCE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CONFIDENCE_NORM](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CONFIDENCE_NORM.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CONFIDENCE_T](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CONFIDENCE_T.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CONVERT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CONVERT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/COS](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/COS.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/COSH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/COSH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/COT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/COT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/COTH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/COTH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/COUNT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/COUNT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/COUNTA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/COUNTA.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/COUNTBLANK](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/COUNTBLANK.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/COUNTIF](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/COUNTIF.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/COUNTIFS](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/COUNTIFS.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/COUPDAYBS](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/COUPDAYBS.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/COUPDAYS](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/COUPDAYS.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/COUPDAYSNC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/COUPDAYSNC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/COUPNCD](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/COUPNCD.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/COUPNUM](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/COUPNUM.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/COUPPCD](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/COUPPCD.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CRITBINOM](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CRITBINOM.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CSC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CSC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CSCH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CSCH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CUMIPMT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CUMIPMT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/CUMPRINC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/CUMPRINC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DATE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DATE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DATEVALUE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DATEVALUE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DAVERAGE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DAVERAGE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DAY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DAY.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DAYS](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DAYS.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DAYS360](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DAYS360.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DB](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DB.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DCOUNT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DCOUNT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DCOUNTA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DCOUNTA.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DDB](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DDB.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DEC2BIN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DEC2BIN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DEC2HEX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DEC2HEX.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DEC2OCT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DEC2OCT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DECIMAL](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DECIMAL.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DEGREES](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DEGREES.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DELTA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DELTA.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DEVSQ](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DEVSQ.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DGET](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DGET.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DISC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DISC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DMAX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DMAX.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DMIN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DMIN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DOLLAR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DOLLAR.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DOLLARDE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DOLLARDE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DOLLARFR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DOLLARFR.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DPRODUCT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DPRODUCT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DSTDEV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DSTDEV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DSTDEVP](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DSTDEVP.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DSUM](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DSUM.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DURATION](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DURATION.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DVAR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DVAR.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/DVARP](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/DVARP.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ECMA_CEILING](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ECMA_CEILING.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/EDATE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/EDATE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/EFFECT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/EFFECT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/EOMONTH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/EOMONTH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ERF](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ERF.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ERF_PRECISE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ERF_PRECISE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ERFC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ERFC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ERFC_PRECISE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ERFC_PRECISE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ERROR_TYPE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ERROR_TYPE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/EVEN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/EVEN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/EXACT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/EXACT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/EXP](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/EXP.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/EXPON_DIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/EXPON_DIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/EXPONDIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/EXPONDIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/F_DIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/F_DIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/F_DIST_RT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/F_DIST_RT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/F_INV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/F_INV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/F_INV_RT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/F_INV_RT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FACT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FACT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FACTDOUBLE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FACTDOUBLE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FALSE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FALSE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FDIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FDIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FIND](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FIND.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FINDB](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FINDB.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FINV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FINV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FISHER](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FISHER.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FISHERINV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FISHERINV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FIXED](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FIXED.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FLOOR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FLOOR.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FLOOR_MATH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FLOOR_MATH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FLOOR_PRECISE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FLOOR_PRECISE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FORECAST_ETS](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FORECAST_ETS.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FORECAST_ETS_CONFINT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FORECAST_ETS_CONFINT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FORECAST_ETS_SEASONALITY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FORECAST_ETS_SEASONALITY.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FORECAST_ETS_STAT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FORECAST_ETS_STAT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FREQUENCY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FREQUENCY.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/FVSCHEDULE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/FVSCHEDULE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/GAMMA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/GAMMA.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/GAMMA_DIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/GAMMA_DIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/GAMMA_INV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/GAMMA_INV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/GAMMADIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/GAMMADIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/GAMMAINV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/GAMMAINV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/GAMMALN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/GAMMALN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/GAMMALN_PRECISE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/GAMMALN_PRECISE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/GAUSS](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/GAUSS.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/GCD](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/GCD.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/GEOMEAN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/GEOMEAN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/GESTEP](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/GESTEP.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/GROWTH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/GROWTH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/HARMEAN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/HARMEAN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/HEX2BIN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/HEX2BIN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/HEX2DEC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/HEX2DEC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/HEX2OCT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/HEX2OCT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/HLOOKUP](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/HLOOKUP.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/HOUR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/HOUR.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/HYPERLINK](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/HYPERLINK.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/HYPGEOM_DIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/HYPGEOM_DIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/HYPGEOMDIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/HYPGEOMDIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IF](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IF.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IFERROR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IFERROR.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IFNA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IFNA.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMABS](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMABS.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMAGINARY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMAGINARY.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMARGUMENT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMARGUMENT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMCONJUGATE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMCONJUGATE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMCOS](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMCOS.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMCOSH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMCOSH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMCOT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMCOT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMCSC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMCSC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMCSCH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMCSCH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMDIV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMDIV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMEXP](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMEXP.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMLN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMLN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMLOG10](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMLOG10.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMLOG2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMLOG2.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMPOWER](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMPOWER.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMPRODUCT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMPRODUCT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMREAL](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMREAL.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMSEC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMSEC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMSECH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMSECH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMSIN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMSIN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMSINH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMSINH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMSQRT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMSQRT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMSUB](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMSUB.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMSUM](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMSUM.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IMTAN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IMTAN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/INDEX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/INT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/INT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/INTRATE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/INTRATE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IPMT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IPMT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/IRR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/IRR.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ISERR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ISERR.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ISERROR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ISERROR.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ISEVEN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ISEVEN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ISFORMULA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ISFORMULA.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ISLOGICAL](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ISLOGICAL.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ISNA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ISNA.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ISNONTEXT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ISNONTEXT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ISNUMBER](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ISNUMBER.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ISO_CEILING](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ISO_CEILING.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ISODD](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ISODD.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ISOWEEKNUM](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ISOWEEKNUM.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ISPMT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ISPMT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ISREF](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ISREF.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ISTEXT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ISTEXT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/KURT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/KURT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/LARGE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/LARGE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/LCM](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/LCM.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/LEFT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/LEFT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/LEFTB](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/LEFTB.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/LEN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/LEN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/LENB](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/LENB.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/LINEST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/LINEST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/LN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/LN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/LOG](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/LOG.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/LOG10](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/LOG10.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/LOGEST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/LOGEST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/LOGINV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/LOGINV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/LOGNORM_DIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/LOGNORM_DIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/LOGNORM_INV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/LOGNORM_INV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/LOGNORMDIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/LOGNORMDIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/LOOKUP](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/LOOKUP.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/LOWER](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/LOWER.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/MATCH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/MATCH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/MAX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/MAX.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/MAXA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/MAXA.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/MDURATION](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/MDURATION.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/MEDIAN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/MEDIAN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/MID](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/MID.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/MIDB](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/MIDB.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/MIN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/MIN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/MINA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/MINA.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/MINUTE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/MINUTE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/MIRR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/MIRR.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/MOD](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/MOD.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/MONTH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/MONTH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/MROUND](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/MROUND.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/MULTINOMIAL](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/MULTINOMIAL.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/MUNIT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/MUNIT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/N](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/N.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/NA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/NA.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/NEGBINOM_DIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/NEGBINOM_DIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/NEGBINOMDIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/NEGBINOMDIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/NETWORKDAYS](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/NETWORKDAYS.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/NETWORKDAYS_INTL](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/NETWORKDAYS_INTL.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/NOMINAL](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/NOMINAL.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/NORM_DIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/NORM_DIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/NORM_INV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/NORM_INV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/NORM_S_DIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/NORM_S_DIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/NORM_S_INV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/NORM_S_INV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/NORMDIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/NORMDIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/NORMINV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/NORMINV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/NORMSDIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/NORMSDIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/NORMSINV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/NORMSINV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/NOT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/NOT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/NOW](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/NOW.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/NPER](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/NPER.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/NPV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/NPV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/NUMBERVALUE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/NUMBERVALUE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/OCT2BIN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/OCT2BIN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/OCT2DEC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/OCT2DEC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/OCT2HEX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/OCT2HEX.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ODD](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ODD.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ODDFPRICE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ODDFPRICE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ODDFYIELD](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ODDFYIELD.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ODDLPRICE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ODDLPRICE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ODDLYIELD](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ODDLYIELD.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/OR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/OR.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/PDURATION](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/PDURATION.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/PERCENTILE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/PERCENTILE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/PERCENTILE_EXC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/PERCENTILE_EXC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/PERCENTILE_INC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/PERCENTILE_INC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/PERCENTRANK](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/PERCENTRANK.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/PERCENTRANK_EXC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/PERCENTRANK_EXC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/PERCENTRANK_INC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/PERCENTRANK_INC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/PERMUT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/PERMUT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/PERMUTATIONA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/PERMUTATIONA.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/PHI](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/PHI.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/PI](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/PI.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/PMT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/PMT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/POISSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/POISSON.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/POISSON_DIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/POISSON_DIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/POWER](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/POWER.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/PPMT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/PPMT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/PRICE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/PRICE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/PRICEDISC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/PRICEDISC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/PRICEMAT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/PRICEMAT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/PRODUCT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/PRODUCT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/PROPER](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/PROPER.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/PV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/PV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/QUARTILE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/QUARTILE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/QUARTILE_EXC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/QUARTILE_EXC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/QUARTILE_INC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/QUARTILE_INC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/QUOTIENT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/QUOTIENT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/RADIANS](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/RADIANS.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/RAND](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/RAND.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/RANDBETWEEN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/RANDBETWEEN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/RANK](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/RANK.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/RANK_AVG](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/RANK_AVG.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/RANK_EQ](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/RANK_EQ.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/RATE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/RATE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/RECEIVED](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/RECEIVED.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/REPLACE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/REPLACE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/REPLACEB](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/REPLACEB.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/REPT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/REPT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/RIGHT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/RIGHT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/RIGHTB](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/RIGHTB.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ROMAN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ROMAN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ROUND](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ROUND.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ROUNDDOWN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ROUNDDOWN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ROUNDUP](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ROUNDUP.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ROWS](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ROWS.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/RRI](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/RRI.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SEARCH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SEARCH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SEARCHB](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SEARCHB.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SEC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SEC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SECH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SECH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SECOND](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SECOND.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SERIESSUM](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SERIESSUM.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SHEET](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SHEET.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SHEETS](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SHEETS.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SIGN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SIGN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SIN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SIN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SINH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SINH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SKEW](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SKEW.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SKEW_P](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SKEW_P.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SLN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SLN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SMALL](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SMALL.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SQRT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SQRT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SQRTPI](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SQRTPI.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/STANDARDIZE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/STANDARDIZE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/STDEV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/STDEV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/STDEV_P](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/STDEV_P.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/STDEV_S](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/STDEV_S.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/STDEVA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/STDEVA.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/STDEVP](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/STDEVP.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/STDEVPA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/STDEVPA.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SUBSTITUTE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SUBSTITUTE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SUBTOTAL](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SUBTOTAL.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SUM](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SUM.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SUMIF](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SUMIF.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SUMIFS](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SUMIFS.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SUMSQ](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SUMSQ.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/SYD](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/SYD.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/T](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/T.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/T_DIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/T_DIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/T_DIST_2T](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/T_DIST_2T.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/T_DIST_RT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/T_DIST_RT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/T_INV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/T_INV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/T_INV_2T](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/T_INV_2T.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/TAN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/TAN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/TANH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/TANH.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/TBILLEQ](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/TBILLEQ.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/TBILLPRICE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/TBILLPRICE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/TBILLYIELD](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/TBILLYIELD.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/TDIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/TDIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/TEXT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/TEXT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/TIME](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/TIME.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/TIMEVALUE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/TIMEVALUE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/TINV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/TINV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/TODAY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/TODAY.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/TRANSPOSE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/TRANSPOSE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/TREND](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/TREND.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/TRIM](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/TRIM.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/TRIMMEAN](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/TRIMMEAN.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/TRUE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/TRUE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/TRUNC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/TRUNC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/TYPE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/TYPE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/UNICHAR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/UNICHAR.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/UNICODE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/UNICODE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/UPPER](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/UPPER.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/VALUE](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/VALUE.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/VAR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/VAR.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/VAR_P](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/VAR_P.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/VAR_S](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/VAR_S.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/VARA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/VARA.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/VARP](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/VARP.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/VARPA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/VARPA.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/VDB](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/VDB.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/VLOOKUP](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/VLOOKUP.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/WEEKDAY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/WEEKDAY.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/WEEKNUM](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/WEEKNUM.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/WEIBULL](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/WEIBULL.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/WEIBULL_DIST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/WEIBULL_DIST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/WORKDAY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/WORKDAY.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/WORKDAY_INTL](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/WORKDAY_INTL.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/XIRR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/XIRR.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/XNPV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/XNPV.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/XOR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/XOR.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/YEAR](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/YEAR.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/YEARFRAC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/YEARFRAC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/YIELD](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/YIELD.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/YIELDDISC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/YIELDDISC.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/YIELDMAT](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/YIELDMAT.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/Z_TEST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/Z_TEST.md) method to Spreadsheet API.
- Added the [ApiWorksheetFunction/ZTEST](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheetFunction/Methods/ZTEST.md) method to Spreadsheet API.
- Added the `WorksheetFunction` property to the [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api.md) object of Spreadsheet API.

### Protected range methods

- Added the [ApiProtectedRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiProtectedRange.md) class to Spreadsheet API.
- Added the [ApiProtectedRange/AddUser](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiProtectedRange/Methods/AddUser.md) method to Spreadsheet API.
- Added the [ApiProtectedRange/DeleteUser](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiProtectedRange/Methods/DeleteUser.md) method to Spreadsheet API.
- Added the [ApiProtectedRange/GetAllUsers](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiProtectedRange/Methods/GetAllUsers.md) method to Spreadsheet API.
- Added the [ApiProtectedRange/GetUser](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiProtectedRange/Methods/GetUser.md) method to Spreadsheet API.
- Added the [ApiProtectedRange/SetAnyoneType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiProtectedRange/Methods/SetAnyoneType.md) method to Spreadsheet API.
- Added the [ApiProtectedRange/SetRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiProtectedRange/Methods/SetRange.md) method to Spreadsheet API.
- Added the [ApiProtectedRange/SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiProtectedRange/Methods/SetTitle.md) method to Spreadsheet API.
- Added the [ApiProtectedRangeUserInfo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiProtectedRangeUserInfo.md) class to Spreadsheet API.
- Added the [ApiProtectedRangeUserInfo/GetId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiProtectedRangeUserInfo/Methods/GetId.md) method to Spreadsheet API.
- Added the [ApiProtectedRangeUserInfo/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiProtectedRangeUserInfo/Methods/GetName.md) method to Spreadsheet API.
- Added the [ApiProtectedRangeUserInfo/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiProtectedRangeUserInfo/Methods/GetType.md) method to Spreadsheet API.
- Added the [ApiWorksheet/AddProtectedRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/AddProtectedRange.md) method to Spreadsheet API.
- Added the [ApiWorksheet/GetAllProtectedRanges](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/GetAllProtectedRanges.md) method to Spreadsheet API.
- Added the [ApiWorksheet/GetProtectedRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/GetProtectedRange.md) method to Spreadsheet API.
- Added the `AllProtectedRanges` property to the [ApiWorksheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet.md) object of Spreadsheet API.
- Added the [ProtectedRangeUserType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ProtectedRangeUserType.md) type to the simple type definitions.

### Reference style methods

- Added the [Api/GetReferenceStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/GetReferenceStyle.md) method to Spreadsheet API.
- Added the [Api/SetReferenceStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/SetReferenceStyle.md) method to Spreadsheet API.
- Added the `ReferenceStyle` property to the [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api.md) object of Spreadsheet API.
- Added the [ReferenceStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ReferenceStyle.md) type to the simple type definitions.

### Methods for pasting / cutting ranges

- Added the [ApiRange/Cut](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/Cut.md) method to Spreadsheet API.
- Added the [ApiRange/PasteSpecial](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/PasteSpecial.md) method to Spreadsheet API.
- Added the [ApiWorksheet/Paste](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/Paste.md) method to Spreadsheet API.
- Added the [PasteSpecialOperation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/PasteSpecialOperation.md) type to the simple type definitions.
- Added the [PasteType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/PasteType.md) type to the simple type definitions.

### Methods for moving a cursor

- Added the [ApiBlockLvlSdt/MoveCursorOutside](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/MoveCursorOutside.md) method to Document API.
- Added the [ApiFormBase/MoveCursorOutside](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/MoveCursorOutside.md) method to Document API.
- Added the [ApiInlineLvlSdt/MoveCursorOutside](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/MoveCursorOutside.md) method to Document API.

### Custom function methods

- Added the [Api/AddCustomFunction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/AddCustomFunction.md) method to Spreadsheet API.
- Added the [Api/ClearCustomFunctions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/ClearCustomFunctions.md) method to Spreadsheet API.
- Added the [Api/RemoveCustomFunction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/RemoveCustomFunction.md) method to Spreadsheet API.

### RGB color methods

- Added the [ApiUniColor/GetRGB](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiUniColor/Methods/GetRGB.md) method to Document API.
- Added the [ApiColor/GetRGB](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColor/Methods/GetRGB.md) method to Spreadsheet API.

### Chart series methods

- Added the [ApiChart/GetAllSeries](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/GetAllSeries.md) method to Document API.
- Added the [ApiChart/GetChartType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/GetChartType.md) method to Document API.
- Added the [ApiChart/GetSeries](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/GetSeries.md) method to Document API.
- Added the [ApiChartSeries](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChartSeries.md) class to Document API.
- Added the [ApiChartSeries/ChangeChartType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChartSeries/Methods/ChangeChartType.md) method to Document API.
- Added the [ApiChartSeries/GetChartType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChartSeries/Methods/GetChartType.md) method to Document API.
- Added the [ApiChartSeries/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChartSeries/Methods/GetClassType.md) method to Document API.
- Added the [ApiChart/GetAllSeries](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/GetAllSeries.md) method to Spreadsheet API.
- Added the [ApiChart/GetChartType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/GetChartType.md) method to Spreadsheet API.
- Added the [ApiChart/GetSeries](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/GetSeries.md) method to Spreadsheet API.
- Added the [ApiChartSeries](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChartSeries.md) class to Spreadsheet API.
- Added the [ApiChartSeries/ChangeChartType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChartSeries/Methods/ChangeChartType.md) method to Spreadsheet API.
- Added the [ApiChartSeries/GetChartType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChartSeries/Methods/GetChartType.md) method to Spreadsheet API.
- Added the [ApiChartSeries/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChartSeries/Methods/GetClassType.md) method to Spreadsheet API.
- Added the [ApiChart/GetAllSeries](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/GetAllSeries.md) method to Presentation API.
- Added the [ApiChart/GetChartType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/GetChartType.md) method to Presentation API.
- Added the [ApiChart/GetSeries](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/GetSeries.md) method to Presentation API.
- Added the [ApiChartSeries/ChangeChartType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChartSeries/Methods/ChangeChartType.md) method to Presentation API.
- Added the [ApiChartSeries/GetChartType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChartSeries/Methods/GetChartType.md) method to Presentation API.
- Added the [ApiChartSeries/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChartSeries/Methods/GetClassType.md) method to Presentation API.
- Added the `"comboBarLine"`, `"comboBarLineSecondary"`, `"comboCustom"`, and `"unknown"` available values for the [ChartType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ChartType.md) definition.

### Other methods

- Added the [ApiDocument/GetDocumentInfo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetDocumentInfo.md) method to Document API.
- Added the [Api/GetDocumentInfo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/GetDocumentInfo.md) method to Spreadsheet API.
- Added the [ApiPresentation/GetDocumentInfo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetDocumentInfo.md) method to Presentation API.
- Added the [DrawingLockType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/DrawingLockType.md) type to the simple type definitions.
- Added the `nWidth` and `nHeight` parameters to the [ApiPictureForm/SetImage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/SetImage.md) method of Document API.
- Removed the `ApiTable/GetNext` method from Document API.
- Removed the `ApiTable/GetPrevious` method from Document API.
- Removed the `ApiTable/Select` method from Presentation API.

## Version 8.0

### Form methods

- Added the [ApiDocument/GetFormsData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetFormsData.md) method to Document API.
- Added the [ApiDocument/SetFormsData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/SetFormsData.md) method to Document API.

### Freeze panes methods

- Added the [Api/GetFreezePanesType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/GetFreezePanesType.md) method to Spreadsheet API.
- Added the [Api/SetFreezePanesType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/SetFreezePanesType.md) method to Spreadsheet API.
- Added the [ApiFreezePanes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFreezePanes.md) class to Spreadsheet API.
- Added the [ApiFreezePanes/FreezeAt](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFreezePanes/Methods/FreezeAt.md) method to Spreadsheet API.
- Added the [ApiFreezePanes/FreezeColumns](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFreezePanes/Methods/FreezeColumns.md) method to Spreadsheet API.
- Added the [ApiFreezePanes/FreezeRows](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFreezePanes/Methods/FreezeRows.md) method to Spreadsheet API.
- Added the [ApiFreezePanes/GetLocation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFreezePanes/Methods/GetLocation.md) method to Spreadsheet API.
- Added the [ApiFreezePanes/Unfreeze](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFreezePanes/Methods/Unfreeze.md) method to Spreadsheet API.
- Added the [ApiWorksheet/GetFreezePanes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/GetFreezePanes.md) method to Spreadsheet API.
- Added the `FreezePanes` property to the [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api.md) object of Spreadsheet API.
- Added the `FreezePanes` property to the [ApiWorksheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet.md) object of Spreadsheet API.

### Comment methods

- Added the `sUserId` parameter to the [Api/AddComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/AddComment.md) method of Document API.
- Added the `sUserId` parameter to the [ApiBlockLvlSdt/AddComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/AddComment.md) method of Document API.
- Added the `sUserId` parameter to the [ApiDocument/AddComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/AddComment.md) method of Document API.
- Added the `sUserId` parameter to the [ApiInlineLvlSdt/AddComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/AddComment.md) method of Document API.
- Added the `sUserId` parameter to the [ApiParagraph/AddComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/AddComment.md) method of Document API.
- Added the `sUserId` parameter to the [ApiRange/AddComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/AddComment.md) method of Document API.
- Added the `sUserId` parameter to the [ApiRun/AddComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun/Methods/AddComment.md) method of Document API.
- Added the `sUserId` parameter to the [ApiTable/AddComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/AddComment.md) method of Document API.
- Added the [Api/GetAllComments](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/GetAllComments.md) method to Spreadsheet API.
- Added the [ApiComment/AddReply](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiComment/Methods/AddReply.md) method to Presentation API.
- Added the [ApiComment/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiComment/Methods/Delete.md) method to Presentation API.
- Added the [ApiComment/GetAuthorName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiComment/Methods/GetAuthorName.md) method to Presentation API.
- Added the [ApiComment/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiComment/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiComment/GetQuoteText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiComment/Methods/GetQuoteText.md) method to Presentation API.
- Added the [ApiComment/GetRepliesCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiComment/Methods/GetRepliesCount.md) method to Presentation API.
- Added the [ApiComment/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiComment/Methods/GetText.md) method to Presentation API.
- Added the [ApiComment/GetTime](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiComment/Methods/GetTime.md) method to Presentation API.
- Added the [ApiComment/GetTimeUTC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiComment/Methods/GetTimeUTC.md) method to Presentation API.
- Added the [ApiComment/IsSolved](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiComment/Methods/IsSolved.md) method to Presentation API.
- Added the [ApiComment/RemoveReplies](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiComment/Methods/RemoveReplies.md) method to Presentation API.
- Added the [ApiComment/SetAuthorName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiComment/Methods/SetAuthorName.md) method to Presentation API.
- Added the [ApiComment/SetSolved](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiComment/Methods/SetSolved.md) method to Presentation API.
- Added the [ApiComment/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiComment/Methods/SetText.md) method to Presentation API.
- Added the [ApiComment/SetTime](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiComment/Methods/SetTime.md) method to Presentation API.
- Added the [ApiComment/SetTimeUTC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiComment/Methods/SetTimeUTC.md) method to Presentation API.
- Added the [ApiComment/SetUserId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiComment/Methods/SetUserId.md) method to Presentation API.
- Added the [ApiPresentation/GetAllComments](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetAllComments.md) method to Presentation API.

### Section methods

- Added the [ApiSection/GetPageHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSection/Methods/GetPageHeight.md) method to Document API.
- Added the [ApiSection/GetPageWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSection/Methods/GetPageWidth.md) method to Document API.

### Simple types

- Added the [FormData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/FormData.md) object to the simple type definitions.
- Added the [FormSpecificType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/FormSpecificType.md) type to the simple type definitions.
- Added the [FreezePaneType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/FreezePaneType.md) type to the simple type definitions.

### Other methods

- Removed the `ApiBlockLvlSdt/SetBackgroundColor` method from Document API.
- Added the [ApiDocument/AddDrawingToPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/AddDrawingToPage.md) method to Document API.
- Added the `bWithotPaddings` parameter to the [ApiWorksheet/SetColumnWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/SetColumnWidth.md) method of Spreadsheet API.

## Version 7.5

### Methods of combo box / dropdown list content control

- Added the [ApiBlockLvlSdt/GetDropdownList](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/GetDropdownList.md) method to Document API.
- Added the [ApiContentControlList](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlList.md) class to Document API.
- Added the [ApiContentControlList/Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlList/Methods/Add.md) method to Document API.
- Added the [ApiContentControlList/Clear](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlList/Methods/Clear.md) method to Document API.
- Added the [ApiContentControlList/GetAllItems](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlList/Methods/GetAllItems.md) method to Document API.
- Added the [ApiContentControlList/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlList/Methods/GetClassType.md) method to Document API.
- Added the [ApiContentControlList/GetElementsCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlList/Methods/GetElementsCount.md) method to Document API.
- Added the [ApiContentControlList/GetItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlList/Methods/GetItem.md) method to Document API.
- Added the [ApiContentControlList/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlList/Methods/GetParent.md) method to Document API.
- Added the [ApiContentControlListEntry](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlListEntry.md) class to Document API.
- Added the [ApiContentControlListEntry/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlListEntry/Methods/Delete.md) method to Document API.
- Added the [ApiContentControlListEntry/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlListEntry/Methods/GetClassType.md) method to Document API.
- Added the [ApiContentControlListEntry/GetIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlListEntry/Methods/GetIndex.md) method to Document API.
- Added the [ApiContentControlListEntry/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlListEntry/Methods/GetParent.md) method to Document API.
- Added the [ApiContentControlListEntry/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlListEntry/Methods/GetText.md) method to Document API.
- Added the [ApiContentControlListEntry/GetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlListEntry/Methods/GetValue.md) method to Document API.
- Added the [ApiContentControlListEntry/MoveDown](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlListEntry/Methods/MoveDown.md) method to Document API.
- Added the [ApiContentControlListEntry/MoveUp](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlListEntry/Methods/MoveUp.md) method to Document API.
- Added the [ApiContentControlListEntry/Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlListEntry/Methods/Select.md) method to Document API.
- Added the [ApiContentControlListEntry/SetIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlListEntry/Methods/SetIndex.md) method to Document API.
- Added the [ApiContentControlListEntry/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlListEntry/Methods/SetText.md) method to Document API.
- Added the [ApiContentControlListEntry/SetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiContentControlListEntry/Methods/SetValue.md) method to Document API.
- Added the [ApiInlineLvlSdt/GetDropdownList](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/GetDropdownList.md) method to Document API.

### Watermark methods

- Added the [ApiDocument/GetWatermarkSettings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetWatermarkSettings.md) method to Document API.
- Added the [ApiDocument/RemoveWatermark](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/RemoveWatermark.md) method to Document API.
- Added the [ApiDocument/SetWatermarkSettings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/SetWatermarkSettings.md) method to Document API.
- Added the [ApiWatermarkSettings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiWatermarkSettings.md) class to Document API.
- Added the [ApiWatermarkSettings/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiWatermarkSettings/Methods/GetClassType.md) method to Document API.
- Added the [ApiWatermarkSettings/GetDirection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiWatermarkSettings/Methods/GetDirection.md) method to Document API.
- Added the [ApiWatermarkSettings/GetImageHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiWatermarkSettings/Methods/GetImageHeight.md) method to Document API.
- Added the [ApiWatermarkSettings/GetImageURL](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiWatermarkSettings/Methods/GetImageURL.md) method to Document API.
- Added the [ApiWatermarkSettings/GetImageWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiWatermarkSettings/Methods/GetImageWidth.md) method to Document API.
- Added the [ApiWatermarkSettings/GetOpacity](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiWatermarkSettings/Methods/GetOpacity.md) method to Document API.
- Added the [ApiWatermarkSettings/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiWatermarkSettings/Methods/GetText.md) method to Document API.
- Added the [ApiWatermarkSettings/GetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiWatermarkSettings/Methods/GetTextPr.md) method to Document API.
- Added the [ApiWatermarkSettings/GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiWatermarkSettings/Methods/GetType.md) method to Document API.
- Added the [ApiWatermarkSettings/SetDirection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiWatermarkSettings/Methods/SetDirection.md) method to Document API.
- Added the [ApiWatermarkSettings/SetImageSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiWatermarkSettings/Methods/SetImageSize.md) method to Document API.
- Added the [ApiWatermarkSettings/SetImageURL](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiWatermarkSettings/Methods/SetImageURL.md) method to Document API.
- Added the [ApiWatermarkSettings/SetOpacity](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiWatermarkSettings/Methods/SetOpacity.md) method to Document API.
- Added the [ApiWatermarkSettings/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiWatermarkSettings/Methods/SetText.md) method to Document API.
- Added the [ApiWatermarkSettings/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiWatermarkSettings/Methods/SetTextPr.md) method to Document API.
- Added the [ApiWatermarkSettings/SetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiWatermarkSettings/Methods/SetType.md) method to Document API.

### Simple types

- Added the [SearchData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/SearchData.md) object to the simple type definitions.
- Added the [ReplaceData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ReplaceData.md) object to the simple type definitions.

### Slide methods

- Added the [ApiSlide/GetVisible](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/GetVisible.md) method to Presentation API.
- Added the [ApiSlide/SetVisible](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/SetVisible.md) method to Presentation API.

## Version 7.4

### Characters methods

- Added the [ApiCharacters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCharacters.md) class to Spreadsheet API.
- Added the [ApiCharacters/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCharacters/Methods/Delete.md) method to Spreadsheet API.
- Added the [ApiCharacters/GetCaption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCharacters/Methods/GetCaption.md) method to Spreadsheet API.
- Added the [ApiCharacters/GetCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCharacters/Methods/GetCount.md) method to Spreadsheet API.
- Added the [ApiCharacters/GetFont](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCharacters/Methods/GetFont.md) method to Spreadsheet API.
- Added the [ApiCharacters/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCharacters/Methods/GetParent.md) method to Spreadsheet API.
- Added the [ApiCharacters/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCharacters/Methods/GetText.md) method to Spreadsheet API.
- Added the [ApiCharacters/Insert](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCharacters/Methods/Insert.md) method to Spreadsheet API.
- Added the [ApiCharacters/SetCaption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCharacters/Methods/SetCaption.md) method to Spreadsheet API.
- Added the [ApiCharacters/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCharacters/Methods/SetText.md) method to Spreadsheet API.

### Font methods

- Added the [ApiFont](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont.md) class to Spreadsheet API.
- Added the [ApiFont/GetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont/Methods/GetBold.md) method to Spreadsheet API.
- Added the [ApiFont/GetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont/Methods/GetColor.md) method to Spreadsheet API.
- Added the [ApiFont/GetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont/Methods/GetItalic.md) method to Spreadsheet API.
- Added the [ApiFont/GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont/Methods/GetName.md) method to Spreadsheet API.
- Added the [ApiFont/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont/Methods/GetParent.md) method to Spreadsheet API.
- Added the [ApiFont/GetSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont/Methods/GetSize.md) method to Spreadsheet API.
- Added the [ApiFont/GetStrikethrough](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont/Methods/GetStrikethrough.md) method to Spreadsheet API.
- Added the [ApiFont/GetSubscript](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont/Methods/GetSubscript.md) method to Spreadsheet API.
- Added the [ApiFont/GetSuperscript](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont/Methods/GetSuperscript.md) method to Spreadsheet API.
- Added the [ApiFont/GetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont/Methods/GetUnderline.md) method to Spreadsheet API.
- Added the [ApiFont/SetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont/Methods/SetBold.md) method to Spreadsheet API.
- Added the [ApiFont/SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont/Methods/SetColor.md) method to Spreadsheet API.
- Added the [ApiFont/SetItalic](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont/Methods/SetItalic.md) method to Spreadsheet API.
- Added the [ApiFont/SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont/Methods/SetName.md) method to Spreadsheet API.
- Added the [ApiFont/SetSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont/Methods/SetSize.md) method to Spreadsheet API.
- Added the [ApiFont/SetStrikethrough](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont/Methods/SetStrikethrough.md) method to Spreadsheet API.
- Added the [ApiFont/SetSubscript](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont/Methods/SetSubscript.md) method to Spreadsheet API.
- Added the [ApiFont/SetSuperscript](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont/Methods/SetSuperscript.md) method to Spreadsheet API.
- Added the [ApiFont/SetUnderline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont/Methods/SetUnderline.md) method to Spreadsheet API.

### Range methods

- Added the [ApiRange/Find](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/Find.md) class to Spreadsheet API.
- Added the [ApiRange/FindNext](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/FindNext.md) class to Spreadsheet API.
- Added the [ApiRange/FindPrevious](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/FindPrevious.md) class to Spreadsheet API.
- Added the [ApiRange/GetCharacters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/GetCharacters.md) class to Spreadsheet API.
- Added the [ApiRange/Replace](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/Replace.md) class to Spreadsheet API.

### Other methods

- Added the [ApiComment/GetId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/GetId.md) method to Document API.
- Added the [ApiDocument/GetAllStyles](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetAllStyles.md) method to Document API.
- Added the [ApiParagraph/GetSection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/GetSection.md) method to Document API.
- Added the resulting string display properties to the [ApiParagraph/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/GetText.md) method to Document API.
- Added the [ApiParagraph/SetSection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/SetSection.md) method to Document API.
- Added the resulting string display properties to the [ApiRange/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/GetText.md) method to Document API.
- Added the [ApiRun/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun/Methods/GetText.md) method to Document API.
- Added the [ApiTable/AddCaption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/AddCaption.md) method to Document API.
- Added the [ApiBlockLvlSdt/AddCaption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/AddCaption.md) method to Document API.
- Added the [Api/GetFullName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/GetFullName.md) method to Document API.
- Added the [Api/GetFullName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/GetFullName.md) method to Spreadsheet API.
- Added the [ApiRange/GetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/GetNumberFormat.md) method to Spreadsheet API.
- Added the [ApiWorksheet/Move](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/Move.md) method to Spreadsheet API.
- Added the [Api/GetFullName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/GetFullName.md) method to Presentation API.

## Version 7.3

### Comment methods

- Added the [ApiBlockLvlSdt/AddComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/AddComment.md) method to Document API.
- Added the [ApiComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment.md) class to Document API.
- Added the [ApiComment/AddReply](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/AddReply.md) method to Document API.
- Added the [ApiComment/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/Delete.md) method to Document API.
- Added the [ApiComment/GetAuthorName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/GetAuthorName.md) method to Document API.
- Added the [ApiComment/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/GetClassType.md) method to Document API.
- Added the [ApiComment/GetQuoteText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/GetQuoteText.md) method to Document API.
- Added the [ApiComment/GetRepliesCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/GetRepliesCount.md) method to Document API.
- Added the [ApiComment/GetReply](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/GetReply.md) method to Document API.
- Added the [ApiComment/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/GetText.md) method to Document API.
- Added the [ApiComment/GetTime](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/GetTime.md) method to Document API.
- Added the [ApiComment/GetTimeUTC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/GetTimeUTC.md) method to Document API.
- Added the [ApiComment/GetUserId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/GetUserId.md) method to Document API.
- Added the [ApiComment/IsSolved](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/IsSolved.md) method to Document API.
- Added the [ApiComment/RemoveReplies](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/RemoveReplies.md) method to Document API.
- Added the [ApiComment/SetAuthorName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/SetAuthorName.md) method to Document API.
- Added the [ApiComment/SetSolved](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/SetSolved.md) method to Document API.
- Added the [ApiComment/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/SetText.md) method to Document API.
- Added the [ApiComment/SetTime](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/SetTime.md) method to Document API.
- Added the [ApiComment/SetTimeUTC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/SetTimeUTC.md) method to Document API.
- Added the [ApiComment/SetUserId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/SetUserId.md) method to Document API.
- Added the [ApiCommentReply](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCommentReply.md) class to Document API.
- Added the [ApiCommentReply/GetAuthorName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCommentReply/Methods/GetAuthorName.md) method to Document API.
- Added the [ApiCommentReply/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCommentReply/Methods/GetClassType.md) method to Document API.
- Added the [ApiCommentReply/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCommentReply/Methods/GetText.md) method to Document API.
- Added the [ApiCommentReply/GetUserId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCommentReply/Methods/GetUserId.md) method to Document API.
- Added the [ApiCommentReply/SetAuthorName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCommentReply/Methods/SetAuthorName.md) method to Document API.
- Added the [ApiCommentReply/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCommentReply/Methods/SetText.md) method to Document API.
- Added the [ApiCommentReply/SetUserId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCommentReply/Methods/SetUserId.md) method to Document API.
- Added the [ApiDocument/GetAllComments](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetAllComments.md) method to Document API.
- Added the [ApiDocument/GetCommentById](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetCommentById.md) method to Document API.
- Added the [ApiInlineLvlSdt/AddComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/AddComment.md) method to Document API.
- Added the [ApiRange/AddComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/AddComment.md) method to Document API.
- Added the [ApiRun/AddComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun/Methods/AddComment.md) method to Document API.
- Added the [ApiTable/AddComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/AddComment.md) method to Document API.
- Added the [Api/GetComments](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/GetComments.md) method to Spreadsheet API.

### Table of contents/figures methods

- Added the [ApiDocument/AddTableOfContents](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/AddTableOfContents.md) method to Document API.
- Added the [ApiDocument/AddTableOfFigures](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/AddTableOfFigures.md) method to Document API.
- Added the [ApiParagraph/AddCaption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/AddCaption.md) method to Document API.

### Other methods

- Added the [ApiDocument/GetPageCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetPageCount.md) method to Document API.
- Added the [ApiDocument/GetStatistics](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetStatistics.md) method to Document API.
- Added the [ApiDocument/SetControlsHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/SetControlsHighlight.md) method to Document API.
- Added the [ApiRange/GetRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/GetRange.md) method to Document API.

## Version 7.2

### Events

- Added the [Api/attachEvent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/attachEvent.md) method to Document API.
- Added the [Api/detachEvent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/detachEvent.md) method to Document API.
- Added the [Api/attachEvent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/attachEvent.md) method to Spreadsheet API.
- Added the [Api/detachEvent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/detachEvent.md) method to Spreadsheet API.
- Added the [Api/attachEvent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/attachEvent.md) method to Presentation API.
- Added the [Api/detachEvent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/detachEvent.md) method to Presentation API.

### Form methods

- Added the [ApiComplexForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm.md) class to Document API.
- Added the [ApiDocument/GetTagsOfAllContentControls](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetTagsOfAllContentControls.md) method to Document API.
- Added the [ApiDocument/GetTagsOfAllForms](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetTagsOfAllForms.md) method to Document API.
- Added the [ApiDocument/GetContentControlsByTag](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetContentControlsByTag.md) method to Document API.
- Added the [ApiDocument/GetFormsByTag](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetFormsByTag.md) method to Document API.

### Methods for converting to/from JSON

- Added the [Api/FromJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/FromJSON.md) method to Document API.
- Added the [ApiBlockLvlSdt/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/ToJSON.md) method to Document API.
- Added the [ApiDocument/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/ToJSON.md) method to Document API.
- Added the [ApiDocumentContent/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/ToJSON.md) method to Document API.
- Added the [ApiDrawing/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/ToJSON.md) method to Document API.
- Added the [ApiFill/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFill/Methods/ToJSON.md) method to Document API.
- Added the [ApiGradientStop/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiGradientStop/Methods/ToJSON.md) method to Document API.
- Added the [ApiHyperlink/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiHyperlink/Methods/ToJSON.md) method to Document API.
- Added the [ApiInlineLvlSdt/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/ToJSON.md) method to Document API.
- Added the [ApiNumbering/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiNumbering/Methods/ToJSON.md) method to Document API.
- Added the [ApiParagraph/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/ToJSON.md) method to Document API.
- Added the [ApiParaPr/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/ToJSON.md) method to Document API.
- Added the [ApiPresetColor/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPresetColor/Methods/ToJSON.md) method to Document API.
- Added the [ApiRange/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/ToJSON.md) method to Document API.
- Added the [ApiRGBColor/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRGBColor/Methods/ToJSON.md) method to Document API.
- Added the [ApiRun/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun/Methods/ToJSON.md) method to Document API.
- Added the [ApiSchemeColor/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSchemeColor/Methods/ToJSON.md) method to Document API.
- Added the [ApiSection/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSection/Methods/ToJSON.md) method to Document API.
- Added the [ApiStroke/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiStroke/Methods/ToJSON.md) method to Document API.
- Added the [ApiStyle/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiStyle/Methods/ToJSON.md) method to Document API.
- Added the [ApiTable/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/ToJSON.md) method to Document API.
- Added the [ApiTableCell/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableCell/Methods/ToJSON.md) method to Document API.
- Added the [ApiTableCellPr/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableCellPr/Methods/ToJSON.md) method to Document API.
- Added the [ApiTablePr/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTablePr/Methods/ToJSON.md) method to Document API.
- Added the [ApiTableRow/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableRow/Methods/ToJSON.md) method to Document API.
- Added the [ApiTableRowPr/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableRowPr/Methods/ToJSON.md) method to Document API.
- Added the [ApiTableStylePr/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableStylePr/Methods/ToJSON.md) method to Document API.
- Added the [ApiTextPr/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/ToJSON.md) method to Document API.
- Added the [ApiUniColor/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiUniColor/Methods/ToJSON.md) method to Document API.
- Added the [Api/FromJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/FromJSON.md) method to Presentation API.
- Added the [ApiDrawing/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/ToJSON.md) method to Presentation API.
- Added the [ApiLayout/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/ToJSON.md) method to Presentation API.
- Added the [ApiMaster/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/ToJSON.md) method to Presentation API.
- Added the [ApiPresentation/SlidesToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/SlidesToJSON.md) method to Presentation API.
- Added the [ApiPresentation/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/ToJSON.md) method to Presentation API.
- Added the [ApiSlide/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/ToJSON.md) method to Presentation API.
- Added the [ApiTable/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTable/Methods/ToJSON.md) method to Presentation API.
- Added the [ApiThemeColorScheme/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeColorScheme/Methods/ToJSON.md) method to Presentation API.
- Added the [ApiThemeFontScheme/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeFontScheme/Methods/ToJSON.md) method to Presentation API.
- Added the [ApiThemeFormatScheme/ToJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeFormatScheme/Methods/ToJSON.md) method to Presentation API.

### Word Art methods

- Added the [Api/CreateWordArt](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateWordArt.md) method to Document API.
- Added the [ApiWorksheet/AddWordArt](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/AddWordArt.md) method to Spreadsheet API.
- Added the [Api/CreateWordArt](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateWordArt.md) method to Presentation API.

### Table of contents/figures methods

- Added the [ApiDocument/UpdateAllTOC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/UpdateAllTOC.md) method to Document API.
- Added the [ApiDocument/UpdateAllTOF](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/UpdateAllTOF.md) method to Document API.

### Footnote/endnote methods

- Added the [ApiDocument/AddEndnote](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/AddEndnote.md) method to Document API.
- Added the [ApiDocument/AddFootnote](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/AddFootnote.md) method to Document API.

### Chart methods

- Added the [ApiChart/ApplyChartStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/ApplyChartStyle.md) method to Document API.
- Added the [ApiChart/RemoveSeria](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/RemoveSeria.md) method to Document API.
- Added the [ApiChart/SetAxisNumFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetAxisNumFormat.md) method to Document API.
- Added the [ApiChart/SetCategoryName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetCategoryName.md) method to Document API.
- Added the [ApiChart/SetDataPointFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetDataPointFill.md) method to Document API.
- Added the [ApiChart/SetDataPointNumFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetDataPointNumFormat.md) method to Document API.
- Added the [ApiChart/SetDataPointOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetDataPointOutLine.md) method to Document API.
- Added the [ApiChart/SetLegendFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetLegendFill.md) method to Document API.
- Added the [ApiChart/SetLegendOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetLegendOutLine.md) method to Document API.
- Added the [ApiChart/SetMarkerFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetMarkerFill.md) method to Document API.
- Added the [ApiChart/SetMarkerOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetMarkerOutLine.md) method to Document API.
- Added the [ApiChart/SetPlotAreaFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetPlotAreaFill.md) method to Document API.
- Added the [ApiChart/SetPlotAreaOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetPlotAreaOutLine.md) method to Document API.
- Added the [ApiChart/SetSeriaName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetSeriaName.md) method to Document API.
- Added the [ApiChart/SetSeriaNumFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetSeriaNumFormat.md) method to Document API.
- Added the [ApiChart/SetSeriaValues](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetSeriaValues.md) method to Document API.
- Added the [ApiChart/SetSeriesFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetSeriesFill.md) method to Document API.
- Added the [ApiChart/SetSeriesOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetSeriesOutLine.md) method to Document API.
- Added the [ApiChart/SetTitleFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetTitleFill.md) method to Document API.
- Added the [ApiChart/SetTitleOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetTitleOutLine.md) method to Document API.
- Added the [ApiChart/SetXValues](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetXValues.md) method to Document API.
- Added the [ApiChart/AddSeria](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/AddSeria.md) method to Spreadsheet API.
- Added the [ApiChart/RemoveSeria](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/RemoveSeria.md) method to Spreadsheet API.
- Added the [ApiChart/SetAxisNumFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetAxisNumFormat.md) method to Spreadsheet API.
- Added the [ApiChart/SetCatFormula](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetCatFormula.md) method to Spreadsheet API.
- Added the [ApiChart/SetDataPointFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetDataPointFill.md) method to Spreadsheet API.
- Added the [ApiChart/SetDataPointOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetDataPointOutLine.md) method to Spreadsheet API.
- Added the [ApiChart/SetLegendFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetLegendFill.md) method to Spreadsheet API.
- Added the [ApiChart/SetLegendOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetLegendOutLine.md) method to Spreadsheet API.
- Added the [ApiChart/SetMarkerFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetMarkerFill.md) method to Spreadsheet API.
- Added the [ApiChart/SetMarkerOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetMarkerOutLine.md) method to Spreadsheet API.
- Added the [ApiChart/SetPlotAreaFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetPlotAreaFill.md) method to Spreadsheet API.
- Added the [ApiChart/SetPlotAreaOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetPlotAreaOutLine.md) method to Spreadsheet API.
- Added the [ApiChart/SetSeriaName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetSeriaName.md) method to Spreadsheet API.
- Added the [ApiChart/SetSeriaValues](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetSeriaValues.md) method to Spreadsheet API.
- Added the [ApiChart/SetSeriaXValues](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetSeriaXValues.md) method to Spreadsheet API.
- Added the [ApiChart/SetSeriesFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetSeriesFill.md) method to Spreadsheet API.
- Added the [ApiChart/SetSeriesOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetSeriesOutLine.md) method to Spreadsheet API.
- Added the [ApiChart/SetTitleFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetTitleFill.md) method to Spreadsheet API.
- Added the [ApiChart/SetTitleOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart/Methods/SetTitleOutLine.md) method to Spreadsheet API.
- Added the [ApiChart/ApplyChartStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/ApplyChartStyle.md) method to Presentation API.
- Added the [ApiChart/RemoveSeria](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/RemoveSeria.md) method to Presentation API.
- Added the [ApiChart/SetAxisNumFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetAxisNumFormat.md) method to Presentation API.
- Added the [ApiChart/SetCategoryName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetCategoryName.md) method to Presentation API.
- Added the [ApiChart/SetDataPointFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetDataPointFill.md) method to Presentation API.
- Added the [ApiChart/SetDataPointNumFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetDataPointNumFormat.md) method to Presentation API.
- Added the [ApiChart/SetDataPointOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetDataPointOutLine.md) method to Presentation API.
- Added the [ApiChart/SetLegendFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetLegendFill.md) method to Presentation API.
- Added the [ApiChart/SetLegendOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetLegendOutLine.md) method to Presentation API.
- Added the [ApiChart/SetMarkerFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetMarkerFill.md) method to Presentation API.
- Added the [ApiChart/SetMarkerOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetMarkerOutLine.md) method to Presentation API.
- Added the [ApiChart/SetPlotAreaFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetPlotAreaFill.md) method to Presentation API.
- Added the [ApiChart/SetPlotAreaOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetPlotAreaOutLine.md) method to Presentation API.
- Added the [ApiChart/SetSeriaName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetSeriaName.md) method to Presentation API.
- Added the [ApiChart/SetSeriaNumFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetSeriaNumFormat.md) method to Presentation API.
- Added the [ApiChart/SetSeriaValues](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetSeriaValues.md) method to Presentation API.
- Added the [ApiChart/SetSeriesFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetSeriesFill.md) method to Presentation API.
- Added the [ApiChart/SetSeriesOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetSeriesOutLine.md) method to Presentation API.
- Added the [ApiChart/SetTitleFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetTitleFill.md) method to Presentation API.
- Added the [ApiChart/SetTitleOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetTitleOutLine.md) method to Presentation API.
- Added the [ApiChart/SetXValues](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetXValues.md) method to Presentation API.

### Drawing methods

- Added the [ApiDocument/GetSelectedDrawings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetSelectedDrawings.md) method to Document API.
- Added the [ApiDocument/ReplaceDrawing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/ReplaceDrawing.md) method to Document API.
- Added the [ApiDocumentContent/GetAllCharts](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/GetAllCharts.md) method to Document API.
- Added the [ApiDocumentContent/GetAllDrawingObjects](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/GetAllDrawingObjects.md) method to Document API.
- Added the [ApiDocumentContent/GetAllImages](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/GetAllImages.md) method to Document API.
- Added the [ApiDocumentContent/GetAllShapes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/GetAllShapes.md) method to Document API.
- Added the [ApiDrawing/GetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/GetHeight.md) method to Document API.
- Added the [ApiDrawing/GetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/GetLockValue.md) method to Document API.
- Added the [ApiDrawing/GetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/GetWidth.md) method to Document API.
- Added the [ApiDrawing/SetDrawingPrFromDrawing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/SetDrawingPrFromDrawing.md) method to Document API.
- Added the [ApiDrawing/SetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/SetLockValue.md) method to Document API.
- Added the [ApiDrawing/GetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/GetHeight.md) method to Spreadsheet API.
- Added the [ApiDrawing/GetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/GetLockValue.md) method to Spreadsheet API.
- Added the [ApiDrawing/GetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/GetWidth.md) method to Spreadsheet API.
- Added the [ApiDrawing/SetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/SetLockValue.md) method to Spreadsheet API.
- Added the [ApiDrawing/GetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/GetHeight.md) method to Presentation API.
- Added the [ApiDrawing/GetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/GetLockValue.md) method to Presentation API.
- Added the [ApiDrawing/GetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/GetWidth.md) method to Presentation API.
- Added the [ApiDrawing/SetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/SetLockValue.md) method to Presentation API.

### OLE object methods

- Added the [ApiOleObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject.md) class to Document API.
- Added the [Api/CreateOleObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateOleObject.md) method to Document API.
- Added the [ApiDocument/GetAllOleObjects](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetAllOleObjects.md) method to Document API.
- Added the [ApiDocumentContent/GetAllOleObjects](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/GetAllOleObjects.md) method to Document API.
- Added the [ApiOleObject/GetApplicationId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/GetApplicationId.md) method to Document API.
- Added the [ApiOleObject/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/GetClassType.md) method to Document API.
- Added the [ApiOleObject/GetData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/GetData.md) method to Document API.
- Added the [ApiOleObject/SetApplicationId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/SetApplicationId.md) method to Document API.
- Added the [ApiOleObject/SetData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject/Methods/SetData.md) method to Document API.
- Added the [ApiParagraph/GetAllOleObjects](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/GetAllOleObjects.md) method to Document API.
- Added the [ApiOleObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject.md) class to Spreadsheet API.
- Added the [ApiWorksheet/AddOleObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/AddOleObject.md) method to Spreadsheet API.
- Added the [ApiWorksheet/GetAllOleObjects](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/GetAllOleObjects.md) method to Spreadsheet API.
- Added the [ApiOleObject/GetApplicationId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetApplicationId.md) method to Spreadsheet API.
- Added the [ApiOleObject/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetClassType.md) method to Spreadsheet API.
- Added the [ApiOleObject/GetData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetData.md) method to Spreadsheet API.
- Added the [ApiOleObject/SetApplicationId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetApplicationId.md) method to Spreadsheet API.
- Added the [ApiOleObject/SetData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetData.md) method to Spreadsheet API.
- Added the [ApiOleObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject.md) class to Presentation API.
- Added the [Api/CreateOleObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateOleObject.md) method to Presentation API.
- Added the [ApiLayout/GetAllOleObjects](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/GetAllOleObjects.md) method to Presentation API.
- Added the [ApiMaster/GetAllOleObjects](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/GetAllOleObjects.md) method to Presentation API.
- Added the [ApiSlide/GetAllOleObjects](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/GetAllOleObjects.md) method to Presentation API.
- Added the [ApiOleObject/GetApplicationId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/GetApplicationId.md) method to Presentation API.
- Added the [ApiOleObject/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiOleObject/GetData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/GetData.md) method to Presentation API.
- Added the [ApiOleObject/SetApplicationId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/SetApplicationId.md) method to Presentation API.
- Added the [ApiOleObject/SetData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiOleObject/Methods/SetData.md) method to Presentation API.

### Table methods

- Added the [ApiTable/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/GetPosInParent.md) method to Document API.
- Added the [ApiTable/GetTableDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/GetTableDescription.md) method to Document API.
- Added the [ApiTable/GetTableTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/GetTableTitle.md) method to Document API.
- Added the [ApiTable/ReplaceByElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/ReplaceByElement.md) method to Document API.
- Added the [ApiTable/SetTableDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/SetTableDescription.md) method to Document API.
- Added the [ApiTable/SetTableTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/SetTableTitle.md) method to Document API.
- Added the [ApiTablePr/GetTableDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTablePr/Methods/GetTableDescription.md) method to Document API.
- Added the [ApiTablePr/GetTableTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTablePr/Methods/GetTableTitle.md) method to Document API.
- Added the [ApiTablePr/SetTableDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTablePr/Methods/SetTableDescription.md) method to Document API.
- Added the [ApiTablePr/SetTableTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTablePr/Methods/SetTableTitle.md) method to Document API.

### Run methods

- Added the [ApiRun/GetFontNames](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun/Methods/GetFontNames.md) method to Document API.
- Added the [ApiRun/SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun/Methods/SetOutLine.md) method to Document API.
- Added the [ApiRun/SetTextFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun/Methods/SetTextFill.md) method to Document API.
- Added the [ApiRun/GetFontNames](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRun/Methods/GetFontNames.md) method to Spreadsheet API.
- Added the [ApiRun/SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRun/Methods/SetOutLine.md) method to Spreadsheet API.
- Added the [ApiRun/SetTextFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRun/Methods/SetTextFill.md) method to Spreadsheet API.
- Added the [ApiRun/GetFontNames](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiRun/Methods/GetFontNames.md) method to Presentation API.
- Added the [ApiRun/SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiRun/Methods/SetOutLine.md) method to Presentation API.
- Added the [ApiRun/SetTextFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiRun/Methods/SetTextFill.md) method to Presentation API.

### Methods for setting text properties

- Added the [ApiTextPr/SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/SetOutLine.md) method to Document API.
- Added the [ApiTextPr/SetTextFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/SetTextFill.md) method to Document API.
- Added the [ApiTextPr/SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextPr/Methods/SetOutLine.md) method to Spreadsheet API.
- Added the [ApiTextPr/SetTextFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextPr/Methods/SetTextFill.md) method to Spreadsheet API.
- Added the [ApiTextPr/SetHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextPr/Methods/SetHighlight.md) method to Presentation API.
- Added the [ApiTextPr/SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextPr/Methods/SetOutLine.md) method to Presentation API.
- Added the [ApiTextPr/SetTextFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTextPr/Methods/SetTextFill.md) method to Presentation API.

### Other methods

- Added the [Api/CreateTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateTextPr.md) method to Document API.
- Added the [ApiBlockLvlSdt/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/GetPosInParent.md) method to Document API.
- Added the [ApiBlockLvlSdt/ReplaceByElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/ReplaceByElement.md) method to Document API.
- Added the [ApiDocument/GetContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetContent.md) method to Document API.
- Added the [ApiDocument/ReplaceCurrentImage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/ReplaceCurrentImage.md) method to Document API.
- Added the [ApiDocumentContent/GetContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/GetContent.md) method to Document API.
- Added the [ApiParagraph/GetFontNames](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/GetFontNames.md) method to Document API.
- Added the [ApiParagraph/GetPosInParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/GetPosInParent.md) method to Document API.
- Added the [ApiParagraph/ReplaceByElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/ReplaceByElement.md) method to Document API.
- Added the [Api/CreateTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/CreateTextPr.md) method to Spreadsheet API.
- Added the [ApiWorksheet/GetAllCharts](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/GetAllCharts.md) method to Spreadsheet API.
- Added the [ApiWorksheet/GetAllDrawings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/GetAllDrawings.md) method to Spreadsheet API.
- Added the [ApiWorksheet/GetAllImages](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/GetAllImages.md) method to Spreadsheet API.
- Added the [ApiWorksheet/GetAllShapes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/GetAllShapes.md) method to Spreadsheet API.
- Added the [Api/CreateTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateTextPr.md) method to Presentation API.
- Added the [ApiParagraph/SetHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiParagraph/Methods/SetHighlight.md) method to Presentation API.
- Added the [ApiPresentation/GetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetHeight.md) method to Presentation API.
- Added the [ApiPresentation/GetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetWidth.md) method to Presentation API.

## Version 7.1

### Form methods

- Added the [Form API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api.md).
- Added the [Api/CreateCheckBoxForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Api/Methods/CreateCheckBoxForm.md) method to Form API.
- Added the [Api/CreateComboBoxForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Api/Methods/CreateComboBoxForm.md) method to Form API.
- Added the [Api/CreatePictureForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Api/Methods/CreatePictureForm.md) method to Form API.
- Added the [Api/CreateTextForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Api/Methods/CreateTextForm.md) method to Form API.
- Added the [ApiBlockLvlSdt/GetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/GetPlaceholderText.md) method to Document API.
- Added the [ApiBlockLvlSdt/SetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt/Methods/SetPlaceholderText.md) method to Document API.
- Added the [ApiCheckBoxForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm.md) class to Document API.
- Added the [ApiCheckBoxForm/Clear](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/Clear.md) method to Document API.
- Added the [ApiCheckBoxForm/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/Copy.md) method to Document API.
- Added the [ApiCheckBoxForm/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/GetClassType.md) method to Document API.
- Added the [ApiCheckBoxForm/GetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/GetFormKey.md) method to Document API.
- Added the [ApiCheckBoxForm/GetFormType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/GetFormType.md) method to Document API.
- Added the [ApiCheckBoxForm/GetRadioGroup](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/GetRadioGroup.md) method to Document API.
- Added the [ApiCheckBoxForm/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/GetText.md) method to Document API.
- Added the [ApiCheckBoxForm/GetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/GetTextPr.md) method to Document API.
- Added the [ApiCheckBoxForm/GetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/GetTipText.md) method to Document API.
- Added the [ApiCheckBoxForm/GetWrapperShape](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/GetWrapperShape.md) method to Document API.
- Added the [ApiCheckBoxForm/IsChecked](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/IsChecked.md) method to Document API.
- Added the [ApiCheckBoxForm/IsFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/IsFixed.md) method to Document API.
- Added the [ApiCheckBoxForm/IsRadioButton](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/IsRadioButton.md) method to Document API.
- Added the [ApiCheckBoxForm/IsRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/IsRequired.md) method to Document API.
- Added the [ApiCheckBoxForm/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/SetBackgroundColor.md) method to Document API.
- Added the [ApiCheckBoxForm/SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/SetBorderColor.md) method to Document API.
- Added the [ApiCheckBoxForm/SetChecked](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/SetChecked.md) method to Document API.
- Added the [ApiCheckBoxForm/SetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/SetFormKey.md) method to Document API.
- Added the [ApiCheckBoxForm/SetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/SetPlaceholderText.md) method to Document API.
- Added the [ApiCheckBoxForm/SetRadioGroup](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/SetRadioGroup.md) method to Document API.
- Added the [ApiCheckBoxForm/SetRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/SetRequired.md) method to Document API.
- Added the [ApiCheckBoxForm/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/SetTextPr.md) method to Document API.
- Added the [ApiCheckBoxForm/SetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/SetTipText.md) method to Document API.
- Added the [ApiCheckBoxForm/ToFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/ToFixed.md) method to Document API.
- Added the [ApiCheckBoxForm/ToInline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm/Methods/ToInline.md) method to Document API.
- Added the [ApiComboBoxForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm.md) class to Document API.
- Added the [ApiComboBoxForm/Clear](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/Clear.md) method to Document API.
- Added the [ApiComboBoxForm/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/Copy.md) method to Document API.
- Added the [ApiComboBoxForm/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/GetClassType.md) method to Document API.
- Added the [ApiComboBoxForm/GetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/GetFormKey.md) method to Document API.
- Added the [ApiComboBoxForm/GetFormType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/GetFormType.md) method to Document API.
- Added the [ApiComboBoxForm/GetListValues](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/GetListValues.md) method to Document API.
- Added the [ApiComboBoxForm/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/GetText.md) method to Document API.
- Added the [ApiComboBoxForm/GetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/GetTextPr.md) method to Document API.
- Added the [ApiComboBoxForm/GetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/GetTipText.md) method to Document API.
- Added the [ApiComboBoxForm/GetWrapperShape](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/GetWrapperShape.md) method to Document API.
- Added the [ApiComboBoxForm/IsEditable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/IsEditable.md) method to Document API.
- Added the [ApiComboBoxForm/IsFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/IsFixed.md) method to Document API.
- Added the [ApiComboBoxForm/IsRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/IsRequired.md) method to Document API.
- Added the [ApiComboBoxForm/SelectListValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/SelectListValue.md) method to Document API.
- Added the [ApiComboBoxForm/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/SetBackgroundColor.md) method to Document API.
- Added the [ApiComboBoxForm/SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/SetBorderColor.md) method to Document API.
- Added the [ApiComboBoxForm/SetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/SetFormKey.md) method to Document API.
- Added the [ApiComboBoxForm/SetListValues](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/SetListValues.md) method to Document API.
- Added the [ApiComboBoxForm/SetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/SetPlaceholderText.md) method to Document API.
- Added the [ApiComboBoxForm/SetRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/SetRequired.md) method to Document API.
- Added the [ApiComboBoxForm/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/SetText.md) method to Document API.
- Added the [ApiComboBoxForm/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/SetTextPr.md) method to Document API.
- Added the [ApiComboBoxForm/SetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/SetTipText.md) method to Document API.
- Added the [ApiComboBoxForm/ToFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/ToFixed.md) method to Document API.
- Added the [ApiComboBoxForm/ToInline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm/Methods/ToInline.md) method to Document API.
- Added the [ApiDocument/ClearAllFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/ClearAllFields.md) method to Document API.
- Added the [ApiDocument/GetAllForms](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetAllForms.md) method to Document API.
- Added the [ApiDocument/SetFormsHighlight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/SetFormsHighlight.md) method to Document API.
- Added the [ApiFormBase](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase.md) class to Document API.
- Added the [ApiFormBase/Clear](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/Clear.md) method to Document API.
- Added the [ApiFormBase/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/Copy.md) method to Document API.
- Added the [ApiFormBase/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetClassType.md) method to Document API.
- Added the [ApiFormBase/GetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetFormKey.md) method to Document API.
- Added the [ApiFormBase/GetFormType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetFormType.md) method to Document API.
- Added the [ApiFormBase/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetText.md) method to Document API.
- Added the [ApiFormBase/GetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetTextPr.md) method to Document API.
- Added the [ApiFormBase/GetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetTipText.md) method to Document API.
- Added the [ApiFormBase/GetWrapperShape](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetWrapperShape.md) method to Document API.
- Added the [ApiFormBase/IsFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/IsFixed.md) method to Document API.
- Added the [ApiFormBase/IsRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/IsRequired.md) method to Document API.
- Added the [ApiFormBase/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetBackgroundColor.md) method to Document API.
- Added the [ApiFormBase/SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetBorderColor.md) method to Document API.
- Added the [ApiFormBase/SetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetFormKey.md) method to Document API.
- Added the [ApiFormBase/SetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetPlaceholderText.md) method to Document API.
- Added the [ApiFormBase/SetRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetRequired.md) method to Document API.
- Added the [ApiFormBase/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetTextPr.md) method to Document API.
- Added the [ApiFormBase/SetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/SetTipText.md) method to Document API.
- Added the [ApiFormBase/ToFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/ToFixed.md) method to Document API.
- Added the [ApiFormBase/ToInline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/ToInline.md) method to Document API.
- Added the [ApiInlineLvlSdt/GetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/GetPlaceholderText.md) method to Document API.
- Added the [ApiInlineLvlSdt/IsForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/IsForm.md) method to Document API.
- Added the [ApiInlineLvlSdt/SetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/SetPlaceholderText.md) method to Document API.
- Added the [ApiPictureForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm.md) class to Document API.
- Added the [ApiPictureForm/Clear](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/Clear.md) method to Document API.
- Added the [ApiPictureForm/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/Copy.md) method to Document API.
- Added the [ApiPictureForm/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/GetClassType.md) method to Document API.
- Added the [ApiPictureForm/GetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/GetFormKey.md) method to Document API.
- Added the [ApiPictureForm/GetFormType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/GetFormType.md) method to Document API.
- Added the [ApiPictureForm/GetImage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/GetImage.md) method to Document API.
- Added the [ApiPictureForm/GetPicturePosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/GetPicturePosition.md) method to Document API.
- Added the [ApiPictureForm/GetScaleFlag](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/GetScaleFlag.md) method to Document API.
- Added the [ApiPictureForm/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/GetText.md) method to Document API.
- Added the [ApiPictureForm/GetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/GetTextPr.md) method to Document API.
- Added the [ApiPictureForm/GetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/GetTipText.md) method to Document API.
- Added the [ApiPictureForm/GetWrapperShape](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/GetWrapperShape.md) method to Document API.
- Added the [ApiPictureForm/IsFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/IsFixed.md) method to Document API.
- Added the [ApiPictureForm/IsLockAspectRatio](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/IsLockAspectRatio.md) method to Document API.
- Added the [ApiPictureForm/IsRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/IsRequired.md) method to Document API.
- Added the [ApiPictureForm/IsRespectBorders](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/IsRespectBorders.md) method to Document API.
- Added the [ApiPictureForm/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/SetBackgroundColor.md) method to Document API.
- Added the [ApiPictureForm/SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/SetBorderColor.md) method to Document API.
- Added the [ApiPictureForm/SetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/SetFormKey.md) method to Document API.
- Added the [ApiPictureForm/SetImage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/SetImage.md) method to Document API.
- Added the [ApiPictureForm/SetLockAspectRatio](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/SetLockAspectRatio.md) method to Document API.
- Added the [ApiPictureForm/SetPicturePosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/SetPicturePosition.md) method to Document API.
- Added the [ApiPictureForm/SetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/SetPlaceholderText.md) method to Document API.
- Added the [ApiPictureForm/SetRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/SetRequired.md) method to Document API.
- Added the [ApiPictureForm/SetRespectBorders](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/SetRespectBorders.md) method to Document API.
- Added the [ApiPictureForm/SetScaleFlag](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/SetScaleFlag.md) method to Document API.
- Added the [ApiPictureForm/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/SetTextPr.md) method to Document API.
- Added the [ApiPictureForm/SetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/SetTipText.md) method to Document API.
- Added the [ApiPictureForm/ToFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/ToFixed.md) method to Document API.
- Added the [ApiPictureForm/ToInline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm/Methods/ToInline.md) method to Document API.
- Added the [ApiTextForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm.md) class to Document API.
- Added the [ApiTextForm/Clear](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/Clear.md) method to Document API.
- Added the [ApiTextForm/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/Copy.md) method to Document API.
- Added the [ApiTextForm/GetCharactersLimit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetCharactersLimit.md) method to Document API.
- Added the [ApiTextForm/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetClassType.md) method to Document API.
- Added the [ApiTextForm/GetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetFormKey.md) method to Document API.
- Added the [ApiTextForm/GetFormType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetFormType.md) method to Document API.
- Added the [ApiTextForm/GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetText.md) method to Document API.
- Added the [ApiTextForm/GetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetTextPr.md) method to Document API.
- Added the [ApiTextForm/GetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetTipText.md) method to Document API.
- Added the [ApiTextForm/GetWrapperShape](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/GetWrapperShape.md) method to Document API.
- Added the [ApiTextForm/IsAutoFit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/IsAutoFit.md) method to Document API.
- Added the [ApiTextForm/IsComb](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/IsComb.md) method to Document API.
- Added the [ApiTextForm/IsFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/IsFixed.md) method to Document API.
- Added the [ApiTextForm/IsMultiline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/IsMultiline.md) method to Document API.
- Added the [ApiTextForm/IsRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/IsRequired.md) method to Document API.
- Added the [ApiTextForm/SetAutoFit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetAutoFit.md) method to Document API.
- Added the [ApiTextForm/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetBackgroundColor.md) method to Document API.
- Added the [ApiTextForm/SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetBorderColor.md) method to Document API.
- Added the [ApiTextForm/SetCellWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetCellWidth.md) method to Document API.
- Added the [ApiTextForm/SetCharactersLimit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetCharactersLimit.md) method to Document API.
- Added the [ApiTextForm/SetComb](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetComb.md) method to Document API.
- Added the [ApiTextForm/SetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetFormKey.md) method to Document API.
- Added the [ApiTextForm/SetMultiline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetMultiline.md) method to Document API.
- Added the [ApiTextForm/SetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetPlaceholderText.md) method to Document API.
- Added the [ApiTextForm/SetRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetRequired.md) method to Document API.
- Added the [ApiTextForm/SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetText.md) method to Document API.
- Added the [ApiTextForm/SetTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetTextPr.md) method to Document API.
- Added the [ApiTextForm/SetTipText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetTipText.md) method to Document API.
- Added the [ApiTextForm/ToFixed](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/ToFixed.md) method to Document API.
- Added the [ApiTextForm/ToInline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/ToInline.md) method to Document API.

### Cross-reference methods

- Added the [ApiDocument/GetAllBookmarksNames](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetAllBookmarksNames.md) method to Document API.
- Added the [ApiDocument/GetAllCaptionParagraphs](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetAllCaptionParagraphs.md) method to Document API.
- Added the [ApiDocument/GetAllHeadingParagraphs](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetAllHeadingParagraphs.md) method to Document API.
- Added the [ApiDocument/GetAllNumberedParagraphs](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetAllNumberedParagraphs.md) method to Document API.
- Added the [ApiDocument/GetEndNotesFirstParagraphs](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetEndNotesFirstParagraphs.md) method to Document API.
- Added the [ApiDocument/GetFootnotesFirstParagraphs](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetFootnotesFirstParagraphs.md) method to Document API.
- Added the [ApiParagraph/AddBookmarkCrossRef](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/AddBookmarkCrossRef.md) method to Document API.
- Added the [ApiParagraph/AddCaptionCrossRef](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/AddCaptionCrossRef.md) method to Document API.
- Added the [ApiParagraph/AddEndnoteCrossRef](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/AddEndnoteCrossRef.md) method to Document API.
- Added the [ApiParagraph/AddFootnoteCrossRef](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/AddFootnoteCrossRef.md) method to Document API.
- Added the [ApiParagraph/AddHeadingCrossRef](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/AddHeadingCrossRef.md) method to Document API.
- Added the [ApiParagraph/AddNumberedCrossRef](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/AddNumberedCrossRef.md) method to Document API.

### Review methods

- Added the [ApiDocument/AcceptAllRevisionChanges](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/AcceptAllRevisionChanges.md) method to Document API.
- Added the [ApiDocument/RejectAllRevisionChanges](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/RejectAllRevisionChanges.md) method to Document API.

### Table background methods

- Added the [ApiTable/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/SetBackgroundColor.md) method to Document API.
- Added the [ApiTableCell/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableCell/Methods/SetBackgroundColor.md) method to Document API.
- Added the [ApiTableCell/SetColumnBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableCell/Methods/SetColumnBackgroundColor.md) method to Document API.
- Added the [ApiTableRow/SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTableRow/Methods/SetBackgroundColor.md) method to Document API.

### Areas methods

- Added the [ApiAreas](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAreas.md) class to Spreadsheet API.
- Added the `Areas` property to the [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) object of Spreadsheet API.
- Added the [ApiAreas/GetCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAreas/Methods/GetCount.md) method to Spreadsheet API.
- Added the [ApiAreas/GetItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAreas/Methods/GetItem.md) method to Spreadsheet API.
- Added the [ApiAreas/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAreas/Methods/GetParent.md) method to Spreadsheet API.

### Range methods

- Added the [ApiRange/AutoFit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/AutoFit.md) method to Spreadsheet API.
- Added the [ApiRange/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/Copy.md) method to Spreadsheet API.
- Added the [ApiRange/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/Delete.md) method to Spreadsheet API.
- Added the [ApiRange/GetAreas](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/GetAreas.md) method to Spreadsheet API.
- Added the [ApiRange/Insert](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/Insert.md) method to Spreadsheet API.
- Added the [ApiRange/Paste](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/Paste.md) method to Spreadsheet API.
- Changed the `data` parameter type of the [ApiRange/SetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/SetValue.md) method of Spreadsheet API.

### Layout methods

- Added the [Api/CreateLayout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateLayout.md) method to Presentation API.
- Added the [ApiLayout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout.md) class to Presentation API.
- Added the [ApiLayout/AddObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/AddObject.md) method to Presentation API.
- Added the [ApiLayout/ClearBackground](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/ClearBackground.md) method to Presentation API.
- Added the [ApiLayout/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/Copy.md) method to Presentation API.
- Added the [ApiLayout/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/Delete.md) method to Presentation API.
- Added the [ApiLayout/Duplicate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/Duplicate.md) method to Presentation API.
- Added the [ApiLayout/FollowMasterBackground](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/FollowMasterBackground.md) method to Presentation API.
- Added the [ApiLayout/GetAllCharts](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/GetAllCharts.md) method to Presentation API.
- Added the [ApiLayout/GetAllDrawings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/GetAllDrawings.md) method to Presentation API.
- Added the [ApiLayout/GetAllImages](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/GetAllImages.md) method to Presentation API.
- Added the [ApiLayout/GetAllShapes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/GetAllShapes.md) method to Presentation API.
- Added the [ApiLayout/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiLayout/GetMaster](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/GetMaster.md) method to Presentation API.
- Added the [ApiLayout/MoveTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/MoveTo.md) method to Presentation API.
- Added the [ApiLayout/RemoveObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/RemoveObject.md) method to Presentation API.
- Added the [ApiLayout/SetBackground](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/SetBackground.md) method to Presentation API.
- Added the [ApiLayout/SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiLayout/Methods/SetName.md) method to Presentation API.

### Master methods

- Added the [Api/CreateMaster](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateMaster.md) method to Presentation API.
- Added the [ApiMaster](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster.md) class to Presentation API.
- Added the [ApiMaster/AddLayout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/AddLayout.md) method to Presentation API.
- Added the [ApiMaster/AddObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/AddObject.md) method to Presentation API.
- Added the [ApiMaster/ClearBackground](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/ClearBackground.md) method to Presentation API.
- Added the [ApiMaster/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/Copy.md) method to Presentation API.
- Added the [ApiMaster/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/Delete.md) method to Presentation API.
- Added the [ApiMaster/Duplicate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/Duplicate.md) method to Presentation API.
- Added the [ApiMaster/GetAllCharts](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/GetAllCharts.md) method to Presentation API.
- Added the [ApiMaster/GetAllDrawings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/GetAllDrawings.md) method to Presentation API.
- Added the [ApiMaster/GetAllImages](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/GetAllImages.md) method to Presentation API.
- Added the [ApiMaster/GetAllShapes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/GetAllShapes.md) method to Presentation API.
- Added the [ApiMaster/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiMaster/GetLayout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/GetLayout.md) method to Presentation API.
- Added the [ApiMaster/GetLayoutsCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/GetLayoutsCount.md) method to Presentation API.
- Added the [ApiMaster/GetTheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/GetTheme.md) method to Presentation API.
- Added the [ApiMaster/RemoveLayout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/RemoveLayout.md) method to Presentation API.
- Added the [ApiMaster/RemoveObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/RemoveObject.md) method to Presentation API.
- Added the [ApiMaster/SetBackground](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/SetBackground.md) method to Presentation API.
- Added the [ApiMaster/SetTheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster/Methods/SetTheme.md) method to Presentation API.

### Placeholder methods

- Added the [Api/CreatePlaceholder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreatePlaceholder.md) method to Presentation API.
- Added the [ApiPlaceholder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPlaceholder.md) class to Presentation API.
- Added the [ApiPlaceholder/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPlaceholder/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiPlaceholder/SetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPlaceholder/Methods/SetType.md) method to Presentation API.

### Theme methods

- Added the [Api/CreateTheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateTheme.md) method to Presentation API.
- Added the [Api/CreateThemeColorScheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateThemeColorScheme.md) method to Presentation API.
- Added the [Api/CreateThemeFontScheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateThemeFontScheme.md) method to Presentation API.
- Added the [Api/CreateThemeFormatScheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateThemeFormatScheme.md) method to Presentation API.
- Added the [ApiTheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTheme.md) class to Presentation API.
- Added the [ApiTheme/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTheme/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiTheme/GetColorScheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTheme/Methods/GetColorScheme.md) method to Presentation API.
- Added the [ApiTheme/GetFontScheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTheme/Methods/GetFontScheme.md) method to Presentation API.
- Added the [ApiTheme/GetFormatScheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTheme/Methods/GetFormatScheme.md) method to Presentation API.
- Added the [ApiTheme/GetMaster](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTheme/Methods/GetMaster.md) method to Presentation API.
- Added the [ApiTheme/SetColorScheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTheme/Methods/SetColorScheme.md) method to Presentation API.
- Added the [ApiTheme/SetFontScheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTheme/Methods/SetFontScheme.md) method to Presentation API.
- Added the [ApiTheme/SetFormatScheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiTheme/Methods/SetFormatScheme.md) method to Presentation API.
- Added the [ApiThemeColorScheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeColorScheme.md) class to Presentation API.
- Added the [ApiThemeColorScheme/ChangeColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeColorScheme/Methods/ChangeColor.md) method to Presentation API.
- Added the [ApiThemeColorScheme/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeColorScheme/Methods/Copy.md) method to Presentation API.
- Added the [ApiThemeColorScheme/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeColorScheme/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiThemeColorScheme/SetSchemeName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeColorScheme/Methods/SetSchemeName.md) method to Presentation API.
- Added the [ApiThemeFontScheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeFontScheme.md) class to Presentation API.
- Added the [ApiThemeFontScheme/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeFontScheme/Methods/Copy.md) method to Presentation API.
- Added the [ApiThemeFontScheme/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeFontScheme/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiThemeFontScheme/SetFonts](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeFontScheme/Methods/SetFonts.md) method to Presentation API.
- Added the [ApiThemeFontScheme/SetSchemeName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeFontScheme/Methods/SetSchemeName.md) method to Presentation API.
- Added the [ApiThemeFormatScheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeFormatScheme.md) class to Presentation API.
- Added the [ApiThemeFormatScheme/ChangeBgFillStyles](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeFormatScheme/Methods/ChangeBgFillStyles.md) method to Presentation API.
- Added the [ApiThemeFormatScheme/ChangeFillStyles](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeFormatScheme/Methods/ChangeFillStyles.md) method to Presentation API.
- Added the [ApiThemeFormatScheme/ChangeLineStyles](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeFormatScheme/Methods/ChangeLineStyles.md) method to Presentation API.
- Added the [ApiThemeFormatScheme/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeFormatScheme/Methods/Copy.md) method to Presentation API.
- Added the [ApiThemeFormatScheme/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeFormatScheme/Methods/GetClassType.md) method to Presentation API.
- Added the [ApiThemeFormatScheme/SetSchemeName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiThemeFormatScheme/Methods/SetSchemeName.md) method to Presentation API.

### Drawing methods

- Added the [ApiDrawing/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/Copy.md) method to Presentation API.
- Added the [ApiDrawing/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/Delete.md) method to Presentation API.
- Added the [ApiDrawing/GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/GetParent.md) method to Presentation API.
- Added the [ApiDrawing/GetParentLayout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/GetParentLayout.md) method to Presentation API.
- Added the [ApiDrawing/GetParentMaster](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/GetParentMaster.md) method to Presentation API.
- Added the [ApiDrawing/GetParentSlide](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/GetParentSlide.md) method to Presentation API.
- Added the [ApiDrawing/GetPlaceholder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/GetPlaceholder.md) method to Presentation API.
- Added the [ApiDrawing/SetPlaceholder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/SetPlaceholder.md) method to Presentation API.

### Slide methods

- Changed the return value for the [ApiSlide/AddObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/AddObject.md) method of Presentation API.
- Added the [ApiSlide/ApplyLayout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/ApplyLayout.md) method to Presentation API.
- Added the [ApiSlide/ApplyTheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/ApplyTheme.md) method to Presentation API.
- Added the [ApiSlide/ClearBackground](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/ClearBackground.md) method to Presentation API.
- Added the [ApiSlide/Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/Copy.md) method to Presentation API.
- Added the [ApiSlide/Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/Delete.md) method to Presentation API.
- Added the [ApiSlide/Duplicate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/Duplicate.md) method to Presentation API.
- Added the [ApiSlide/FollowLayoutBackground](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/FollowLayoutBackground.md) method to Presentation API.
- Added the [ApiSlide/FollowMasterBackground](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/FollowMasterBackground.md) method to Presentation API.
- Added the [ApiSlide/GetAllCharts](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/GetAllCharts.md) method to Presentation API.
- Added the [ApiSlide/GetAllDrawings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/GetAllDrawings.md) method to Presentation API.
- Added the [ApiSlide/GetAllImages](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/GetAllImages.md) method to Presentation API.
- Added the [ApiSlide/GetAllShapes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/GetAllShapes.md) method to Presentation API.
- Added the [ApiSlide/GetLayout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/GetLayout.md) method to Presentation API.
- Added the [ApiSlide/GetSlideIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/GetSlideIndex.md) method to Presentation API.
- Added the [ApiSlide/GetTheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/GetTheme.md) method to Presentation API.
- Added the [ApiSlide/MoveTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/MoveTo.md) method to Presentation API.
- Added the [ApiSlide/RemoveObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiSlide/Methods/RemoveObject.md) method to Presentation API.

### Presentation methods

- Added the [ApiPresentation/AddMaster](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/AddMaster.md) method to Presentation API.
- Added the [ApiPresentation/ApplyTheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/ApplyTheme.md) method to Presentation API.
- Added the [ApiPresentation/GetMaster](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetMaster.md) method to Presentation API.
- Added the [ApiPresentation/GetMastersCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetMastersCount.md) method to Presentation API.
- Added the [ApiPresentation/GetSlidesCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/GetSlidesCount.md) method to Presentation API.
- Added the [ApiPresentation/RemoveSlides](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/RemoveSlides.md) method to Presentation API.

### Other methods

- Added the `sParaTab` and `sParaNewLine` parameters to the [Api/ReplaceTextSmart](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/ReplaceTextSmart.md) method of Document API.
- Added the [ApiInlineLvlSdt/GetParentParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt/Methods/GetParentParagraph.md) method to Document API.
- Removed the `ApiShape/GetDocContent` method from Spreadsheet API.

## Version 7.0

- Added the [Api/ConvertDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/ConvertDocument.md) method to Document API.
- Added the [ApiDocument/ToHtml](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/ToHtml.md) method to Document API.
- Added the [ApiDocument/ToMarkdown](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/ToMarkdown.md) method to Document API.
- Added the [SortOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/SortOrientation.md) simple type.
- Added the [SortHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/SortHeader.md) simple type.
- Added the [SortOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/SortOrder.md) simple type.
- Added the [ApiRange/SetSort](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/SetSort.md) method to Spreadsheet API.
- Added the [Api/RecalculateAllFormulas](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/RecalculateAllFormulas.md) method to Spreadsheet API.
- Added the [ApiPresentation/SetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/SetLanguage.md) method to Presentation API.

## Version 6.4

- Changed the return value of the [Api/CreateRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateRange.md) method of Document API.
- Removed the `Api/GetFirstRunInArray` method from Document API.
- Removed the `Api/GetLastRunInArray` method from Document API.
- Added parameters to the [ApiChart/SetLegendFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiChart/Methods/SetLegendFontSize.md) method of Document API.
- Added parameters to the [ApiDocument/GetElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetElement.md) method of Document API.
- Added the return value to the [ApiDocument/Push](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/Push.md) method of Document API.
- Added parameters to the [ApiDocumentContent/GetElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/GetElement.md) method of Document API.
- Added the return value to the [ApiDocumentContent/Push](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/Push.md) method of Document API.
- Removed parameters from the [ApiRange/Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/Select.md) method of Document API.
- Added the `oCell` parameter to the [ApiTable/AddElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable/Methods/AddElement.md) method of Document API.
- Added parameters to the [Api/GetRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Api/Methods/GetRange.md) method of Spreadsheet API.
- Added the [ApiComment/GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/GetClassType.md) method to Spreadsheet API.
- Removed the `ApiDocument/Last` method from Spreadsheet and Presentation API.
- Added the [ApiRange/GetCols](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/GetCols.md) method to Spreadsheet API.
- Added the [ApiRange/End](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/End.md) method to Spreadsheet API.
- Added the [ApiRange/GetCells](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/GetCells.md) method to Spreadsheet API.
- Added the [ApiRange/GetOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/GetOrientation.md) method to Spreadsheet API.
- Added the [ApiRange/SetOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange/Methods/SetOrientation.md) method to Spreadsheet API.
- Added the `Cols` and `Orientation` properties to the [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) object of Spreadsheet API.
- Added parameters to the [ApiWorksheet/GetCells](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet/Methods/GetCells.md) method of Spreadsheet API.
- Added parameters to the [Api/CreateGroup](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api/Methods/CreateGroup.md) method of Presentation API.
- Added parameters to the [ApiChart/SetLegendFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiChart/Methods/SetLegendFontSize.md) method of Presentation API.
- Added parameters to the [ApiPresentation/ReplaceCurrentImage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiPresentation/Methods/ReplaceCurrentImage.md) method of Presentation API.
