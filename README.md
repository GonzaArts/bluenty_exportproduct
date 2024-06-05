
# Bluenty Export Product Module

## Overview
The Bluenty Export Product module for Magento 2 provides an admin interface to export products to a CSV file with customizable attributes. The module includes filters for product manufacturers and language selection for the exported data.

## Features
- Select product attributes to be exported.
- Filter products by manufacturer.
- Choose the language for product data export.
- Generate CSV files with the selected data.
- List and download generated CSV files from the admin interface.

## Requirements
- Magento 2.4.5-p1
- PHP 7.4 or PHP 8.1

## Installation

1. **Download the Module**

   Download the module and place it in the `app/code/Bluenty/ExportProduct` directory of your Magento installation.

2. **Enable the Module**

   ```bash
   php bin/magento module:enable Bluenty_ExportProduct
   ```

3. **Upgrade the Setup**

   ```bash
   php bin/magento setup:upgrade
   ```

4. **Compile and Deploy Static Content**

   ```bash
   php bin/magento setup:di:compile
   php bin/magento setup:static-content:deploy -f
   ```

5. **Clear Cache**

   ```bash
   php bin/magento cache:clean
   php bin/magento cache:flush
   ```

## Usage

1. **Accessing the Module**

   - Log in to the Magento Admin.
   - Navigate to `Bluenty > Export Product` in the main menu.

2. **Exporting Products**

   - In the Export Product page, select the desired product attributes.
   - Choose the manufacturers to filter the products.
   - Select the language for the product data.
   - Click the `Generate CSV` button to create the export file.

3. **Downloading Exported Files**

   - Below the configuration form, a list of generated CSV files will be displayed.
   - Click on the download link to download the desired file.

## File Structure

```
app/code/Bluenty/ExportProduct/
├── Block/
│   ├── Adminhtml/
│   │   ├── Export.php
│   │   └── FileList.php
├── Controller/
│   ├── Adminhtml/
│   │   ├── Export/
│   │   │   ├── Generate.php
│   │   │   └── Index.php
│   │   └── File/
│   │       └── Download.php
├── etc/
│   ├── adminhtml/
│   │   ├── di.xml
│   │   ├── menu.xml
│   │   ├── routes.xml
│   │   └── system.xml
│   ├── acl.xml
│   └── module.xml
├── Helper/
│   └── Data.php
├── i18n/
│   └── en_US.csv
├── Model/
│   ├── Export.php
│   └── ExportFile.php
├── Setup/
│   └── InstallSchema.php
├── Ui/
│   └── Component/
│       └── Listing/
│           └── Column/
│               └── Actions.php
├── view/
│   ├── adminhtml/
│   │   ├── layout/
│   │   │   └── exportproduct_index_index.xml
│   │   ├── templates/
│   │   │   ├── export/
│   │   │   │   └── index.phtml
│   │   │   └── filelist/
│   │   │       └── index.phtml
├── registration.php
└── composer.json
```

## File Descriptions

- **Block/Adminhtml/Export.php**: Logic for rendering the export form.
- **Block/Adminhtml/FileList.php**: Logic for rendering the list of exported files.
- **Controller/Adminhtml/Export/Generate.php**: Controller to handle CSV generation.
- **Controller/Adminhtml/Export/Index.php**: Controller to render the export page.
- **Controller/Adminhtml/File/Download.php**: Controller to handle file downloads.
- **etc/adminhtml/di.xml**: Dependency injection configurations.
- **etc/adminhtml/menu.xml**: Admin menu configurations.
- **etc/adminhtml/routes.xml**: Admin route configurations.
- **etc/adminhtml/system.xml**: System configuration settings.
- **etc/acl.xml**: Access control list configurations.
- **etc/module.xml**: Module configuration file.
- **Helper/Data.php**: Helper functions.
- **i18n/en_US.csv**: Translation file.
- **Model/Export.php**: Model logic for exporting data.
- **Model/ExportFile.php**: Model for handling exported files.
- **Setup/InstallSchema.php**: Database schema setup.
- **Ui/Component/Listing/Column/Actions.php**: UI component for listing actions.
- **view/adminhtml/layout/exportproduct_index_index.xml**: Layout XML for the export product page.
- **view/adminhtml/templates/export/index.phtml**: Template file for the export form.
- **view/adminhtml/templates/filelist/index.phtml**: Template file for the file list.
- **registration.php**: Module registration file.
- **composer.json**: Composer configuration file.

## Support

For any issues or feature requests, please open an issue on the GitHub repository.

## License

This project is licensed under the MIT License.
