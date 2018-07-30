# contact-form-7-phone-field-with-flag-and-extension
Custom code for contact form 7 WordPress plugin. Code helps modify the Telephone/Phone number field. Script will show country number prefix extension with country flags.

<img src="https://github.com/narinderbisht/contact-form-7-phone-field-with-flag-and-extension/blob/master/screenshot.png" alt="screenshot"/>

## Getting Started
1. Download the [latest release](https://github.com/narinderbisht/contact-form-7-phone-field-with-flag-and-extension/releases/latest).

2. Uzip the folder. Copy nb_country Folder inside your wordpress active theme root. web_root/wp-content/themes/active_theme

3. Edit your theme functions.php file. Paste the following code at the end of the file or any other perfect place according to your theme code.

```php

function nb_internationPhoneCssJs() {
    wp_enqueue_style( 'nb-intlTelInput-style', get_stylesheet_directory_uri() . '/nb_intl/css/intlTelInput.min.css' );
	wp_enqueue_script( 'nb-intlTelInput-script', get_stylesheet_directory_uri() . '/nb_intl/js/intlTelInput.min.js', array( 'jquery' ) );
	wp_enqueue_script( 'nb-intlTelInput-custom-script', get_stylesheet_directory_uri() . '/nb_intl/js/custom_script.js', array( 'jquery' ) );
    
}
add_action( 'wp_enqueue_scripts', 'nb_internationPhoneCssJs' );
```

4. Add telephone type input in your contact form. You can use custom css class or ID attribute. But same ID/Class attribute should be use in custom_script.js file Jquery elelemnt sepecifier. Current specifier will display flag drop down on all telephone number fields.
For example: .wpcf7-tel
```js
(function($) {
        $(function() {
            $(".wpcf7-tel").intlTelInput({
              // allowDropdown: false,
              // autoHideDialCode: false,
               autoPlaceholder: "off",
              // dropdownContainer: "body",
              // excludeCountries: ["us"],
              // formatOnDisplay: false,
              // geoIpLookup: function(callback) {
              //   $.get("http://ipinfo.io", function() {}, "jsonp").always(function(resp) {
              //     var countryCode = (resp && resp.country) ? resp.country : "";
              //     callback(countryCode);
              //   });
              // },
               hiddenInput: "full_number",
              // initialCountry: "auto",
              // localizedCountries: { 'de': 'Deutschland' },
               nationalMode: false,
              // onlyCountries: ['us', 'gb', 'ch', 'ca', 'do'],
              // placeholderNumberType: "MOBILE",
              // preferredCountries: ['cn', 'jp'],
               //separateDialCode: true,
              //utilsScript: "nb_intl/js/utils.js"
            });
        });
})(jQuery);
})(jQuery);
```

# Reference

1. https://github.com/jackocnr/intl-tel-input

# Author website and blog

http://narindersingh.in
