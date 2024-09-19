# [Gathered by cupent](https://www.cupent.com)
Create Date: 19-09-2024
Last Update Date: 19-09-2024

# Complete Guide for Setting Up XAMPP, PHP, Composer,Node.js and Formatter(php-cs-fixer).

## 1. Installing XAMPP

XAMPP is a free and open-source web server solution stack that includes Apache, MySQL, and PHP.

### Steps:
1. **Download XAMPP**  
   Visit the official XAMPP download page: [XAMPP Downloads](https://www.apachefriends.org/index.html).  
   Choose the appropriate version for your operating system (Windows, macOS, Linux).

2. **Install XAMPP**  
   Run the installer and follow the on-screen instructions.  
   Ensure Apache and MySQL are selected during installation.

3. **Start XAMPP**  
   Open **XAMPP Control Panel**.  
   Start the **Apache** and **MySQL** services.

### Verify the Installation:
- Open your browser and go to `http://localhost/`.  
  You should see the XAMPP welcome page.

---

## 2. Installing PHP

XAMPP includes PHP by default. However, if you need to install PHP separately, follow the steps below.

### Steps:
1. **Download PHP**  
   Visit the official PHP download page: [PHP Downloads](https://www.php.net/downloads).  
   Download the version compatible with your operating system (Windows/macOS/Linux).

2. **Set PHP Path (Windows)**  
   Extract the downloaded PHP folder (e.g., `php-8.x.x`).  
   Go to **System Properties** > **Advanced** > **Environment Variables**.  
   Under **System variables**, find the **Path** variable, select it, and click **Edit**.  
   Add a new entry with the path to your PHP folder (e.g., `C:\php`).

3. **Verify the PHP Installation**  
   Open the command prompt and run:
   ```bash
   php -v
   ```
   
   ## 3. Installing Composer

Composer is a dependency manager for PHP and is required for Laravel installation.

### Steps:

1. **Download Composer**  
   Visit the official Composer website: [Composer Download](https://getcomposer.org/download/).  
   Download and run **Composer-Setup.exe** for Windows, or follow the instructions for macOS/Linux.

2. **Install Composer**  
   Run the installer and follow the on-screen instructions.  
   If prompted, select the correct PHP path during installation.

3. **Verify the Composer Installation**  
   Open the terminal or command prompt and run:
   ```bash
   composer -v
   ```

## 4. Installing Node.js

Node.js is required for compiling frontend assets using Laravel Mix and for npm (Node Package Manager).

### Steps:

1. **Download Node.js**  
   Visit the official Node.js website: [Node.js Downloads](https://nodejs.org/en/download/).  
   Choose the **LTS** (Long-Term Support) version for stability.

2. **Install Node.js**  
   Run the installer and follow the on-screen instructions.

3. **Verify the Node.js Installation**  
   Open the terminal or command prompt and run:

  ```bash
     node -v
   ```

## 5. Installing Laravel

Once you have XAMPP, PHP, Composer, and Node.js set up, you can install Laravel.

### Steps:

1. **Open Terminal or Command Prompt**  
   Navigate to the folder where you want to install your Laravel project.

2. **Run Laravel Installation Command**  
   Use Composer to create a new Laravel project by running:

 ```bash
     composer create-project --prefer-dist laravel/laravel project-name
   ```
3. **After the installation is complete, navigate into the project folder**

  ```bash
      cd project-name
   ```

5. **Start the development server**
   
  ```bash
      php artisan serve
   ```

7. **Open your browser and go to [http://localhost:8000/](http://localhost:8000/) to see your Laravel application in action.**

For further commands and details, refer to the [Laravel Code Guide](./Laravel_code_guide.md) and  [Laravel_Quick_Reference](./Laravel_Quick_Reference.md)  

## 6.Setting Up PHP CS Fixer in Visual Studio Code

### Steps:

1. **Open Visual Studio Code**

2. **Go to the Extensions View**
   
   - Click the Extensions icon in the Activity Bar on the side of the window.
   - Alternatively, press `Ctrl+Shift+X` to open the Extensions view.

3. **Search for PHP CS Fixer**
   
   - Type `PHP CS Fixer` into the search bar in the Extensions view.

4. **Install the Extension**
   
   - Find the extension named "PHP CS Fixer" by junstyle.
   - Click the `Install` button to add the extension to your Visual Studio Code setup.

 ## 7.Create a PHP CS Fixer Configuration File

To configure PHP CS Fixer for your project, follow these steps:

### Steps:

1. **Create the Configuration File**

   - In the root directory of your project, create a file named `.php-cs-fixer.php`.

2. **Add Basic Configuration**

   - Add the following basic configuration to the `.php-cs-fixer.php` file:

     ```php
     <?php

     use PhpCsFixer\Config;
     use PhpCsFixer\Finder;

     $rules = [
         'array_indentation' => true,
         'array_syntax' => ['syntax' => 'short'],
         'binary_operator_spaces' => [
             'default' => 'single_space',
             'operators' => ['=>' => null],
         ],
         'blank_line_after_namespace' => true,
         'blank_line_after_opening_tag' => true,
         'blank_line_before_statement' => [
             'statements' => ['return'],
         ],
         'single_space_around_construct' => true,  // Ensures single space around constructs (e.g., if, for)
         'control_structure_braces' => true,  // Manages braces in control structures
         'control_structure_continuation_position' => true,  // Handles continuation braces
         'declare_parentheses' => true,  // Ensures proper parentheses for declare statements
         'no_multiple_statements_per_line' => true,  // Prevents multiple statements on the same line
         'braces' => [
             'position_after_anonymous_constructs' => 'next',
             'position_after_control_structures' => 'next',
             'position_after_functions_and_oop_constructs' => 'next',
         ],  // Correctly handles brace positions
         'statement_indentation' => true,  // Ensures proper indentation inside statements
         'no_extra_blank_lines' => true,  // Removes unnecessary blank lines
         'cast_spaces' => true,
         'class_attributes_separation' => [
             'elements' => [
                 'const' => 'one',
                 'method' => 'one',
                 'property' => 'one',
                 'trait_import' => 'none',
             ],
         ],
         'class_definition' => [
             'multi_line_extends_each_single_line' => true,
             'single_item_single_line' => true,
             'single_line' => true,
         ],
         'concat_space' => [
             'spacing' => 'none',
         ],
         'constant_case' => ['case' => 'lower'],
         'declare_equal_normalize' => true,
         'elseif' => true,
         'encoding' => true,
         'full_opening_tag' => true,
         'fully_qualified_strict_types' => true, // added by Shift
         'function_declaration' => true,
         'type_declaration_spaces' => true,  // Replaces deprecated 'function_typehint_space'
         'general_phpdoc_tag_rename' => true,
         'heredoc_to_nowdoc' => true,
         'include' => true,
         'increment_style' => ['style' => 'post'],
         'indentation_type' => true,
         'linebreak_after_opening_tag' => true,
         'line_ending' => true,
         'lowercase_cast' => true,
         'lowercase_keywords' => true,
         'lowercase_static_reference' => true, // added from Symfony
         'magic_method_casing' => true, // added from Symfony
         'magic_constant_casing' => true,
         'method_argument_space' => [
             'on_multiline' => 'ignore',
         ],
         'multiline_whitespace_before_semicolons' => [
             'strategy' => 'no_multi_line',
         ],
         'native_function_casing' => true,
         'no_alias_functions' => true,
         'no_extra_blank_lines' => [
             'tokens' => [
                 'extra',
                 'throw',
                 'use',
             ],
         ],
         'no_blank_lines_after_class_opening' => true,
         'no_blank_lines_after_phpdoc' => true,
         'no_closing_tag' => true,
         'no_empty_phpdoc' => true,
         'no_empty_statement' => true,
         'no_leading_import_slash' => true,
         'no_leading_namespace_whitespace' => true,
         'no_mixed_echo_print' => [
             'use' => 'echo',
         ],
         'no_multiline_whitespace_around_double_arrow' => true,
         'no_short_bool_cast' => true,
         'no_singleline_whitespace_before_semicolons' => true,
         'no_spaces_after_function_name' => true,
         'no_spaces_around_offset' => [
             'positions' => ['inside', 'outside'],
         ],
         'spaces_inside_parentheses' => true,  // Replaces deprecated 'no_spaces_inside_parenthesis'
         'no_trailing_comma_in_singleline' => true,  // Replaces deprecated 'no_trailing_comma_in_singleline_array'
         'no_trailing_whitespace' => true,
         'no_trailing_whitespace_in_comment' => true,
         'no_unneeded_control_parentheses' => [
             'statements' => ['break', 'clone', 'continue', 'echo_print', 'return', 'switch_case', 'yield'],
         ],
         'no_unreachable_default_argument_value' => true,
         'no_useless_return' => true,
         'no_whitespace_before_comma_in_array' => true,
         'no_whitespace_in_blank_line' => true,
         'normalize_index_brace' => true,
         'not_operator_with_successor_space' => true,
         'object_operator_without_whitespace' => true,
         'ordered_imports' => ['sort_algorithm' => 'alpha'],
         'psr_autoloading' => true,
         'phpdoc_indent' => true,
         'phpdoc_inline_tag_normalizer' => true,
         'phpdoc_no_access' => true,
         'phpdoc_no_package' => true,
         'phpdoc_no_useless_inheritdoc' => true,
         'phpdoc_scalar' => true,
         'phpdoc_single_line_var_spacing' => true,
         'phpdoc_summary' => false,
         'phpdoc_to_comment' => false, // override to preserve user preference
         'phpdoc_tag_type' => true,
         'phpdoc_trim' => true,
         'phpdoc_types' => true,
         'phpdoc_var_without_name' => true,
         'self_accessor' => true,
         'short_scalar_cast' => true,
         'simplified_null_return' => false, // disabled as "risky"
         'single_blank_line_at_eof' => true,
         'blank_lines_before_namespace' => true,  // Replaces deprecated 'single_blank_line_before_namespace'
         'single_class_element_per_statement' => [
             'elements' => ['const', 'property'],
         ],
         'single_import_per_statement' => true,
         'single_line_after_imports' => true,
         'single_line_comment_style' => [
             'comment_types' => ['hash'],
         ],
         'single_quote' => true,
         'space_after_semicolon' => true,
         'standardize_not_equals' => true,
         'switch_case_semicolon_to_colon' => true,
         'switch_case_space' => true,
         'ternary_operator_spaces' => true,
         'trailing_comma_in_multiline' => ['elements' => ['arrays']],
         'trim_array_spaces' => true,
         'unary_operator_spaces' => true,
         'visibility_required' => [
             'elements' => ['method', 'property'],
         ],
         'whitespace_after_comma_in_array' => true,
     ];

     $finder = Finder::create()
         ->in([
             __DIR__ . '/app',
             __DIR__ . '/config',
             __DIR__ . '/database',
             __DIR__ . '/resources',
             __DIR__ . '/routes',
             __DIR__ . '/tests',
         ])
         ->name('*.php')
         ->notName('*.blade.php')
         ->ignoreDotFiles(true)
         ->ignoreVCS(true);

     return (new Config)
         ->setFinder($finder)
         ->setRules($rules)
         ->setRiskyAllowed(true)
         ->setUsingCache(true);
    
     ```

   - This configuration sets PHP CS Fixer to use the PSR-2 coding standard and short array syntax. It also specifies that the fixer should search for PHP files in the current directory (`__DIR__`).

3. **Customize Rules**

   - Modify the rules in the `setRules` method as needed to fit your project's coding standards. Refer to the [PHP CS Fixer documentation](https://github.com/FriendsOfPHP/PHP-CS-Fixer) for additional rules and options.

By following these steps, you will create a PHP CS Fixer configuration file tailored to your project’s needs.
 


## 8.Configure PHP CS Fixer in VS Code

After installing the PHP CS Fixer extension, follow these steps to configure it so that it automatically applies formatting rules when saving a file:

### Steps:

1. **Open the Command Palette**

   - Press `Ctrl+Shift+P` to open the Command Palette.

2. **Open Settings (JSON)**

   - Type and select `Preferences: Open Settings (JSON)`.

3. **Add or Modify Settings**

   - Add or modify the following settings in your `settings.json` file:

    ```json
     {
       "editor.defaultFormatter": "junstyle.php-cs-fixer",
       "notebook.defaultFormatter": "junstyle.php-cs-fixer",
       "editor.formatOnPaste": true,
       "php-cs-fixer.executablePath": "${workspaceRoot}/vendor/bin/php-cs-fixer",
       "php-cs-fixer.onsave": true,
       "php-cs-fixer.exclude": [
         "**/vendor/**/tests/**"
       ]
     }
     ```

    - **`"editor.defaultFormatter": "junstyle.php-cs-fixer"`**: Sets PHP CS Fixer as the default formatter for PHP files.
   - **`"notebook.defaultFormatter": "junstyle.php-cs-fixer"`**: Sets PHP CS Fixer as the default formatter for notebook files.
   - **`"editor.formatOnPaste": true`**: Enables formatting of pasted content.
   - **`"php-cs-fixer.executablePath": "${workspaceRoot}/vendor/bin/php-cs-fixer"`**: Specifies the path to the PHP CS Fixer executable.
   - **`"php-cs-fixer.onsave": true`**: Automatically formats files on save.
   - **`"php-cs-fixer.exclude": ["**/vendor/**/tests/**"]`**: Excludes test files from being formatted.

   - Replace `~/.composer/vendor/bin/php-cs-fixer` with the actual path to the `php-cs-fixer` executable if installed elsewhere.
  
   - By configuring these settings, PHP CS Fixer will be used to format your PHP code automatically whenever you save a file, ensuring consistent coding standards across your project.


4. **Verify Integration**

   - Open a PHP file in Visual Studio Code.
   - Make a change that should trigger formatting according to your PHP CS Fixer rules.
   - Save the file by pressing `Ctrl+S`.
   - Verify that the file is automatically formatted according to the rules specified in your `.php-cs-fixer.dist.php` configuration file.

By completing these steps, PHP CS Fixer will be configured to automatically apply coding standards and formatting rules whenever you save a PHP file in Visual Studio Code.
