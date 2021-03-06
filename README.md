Payment Methods Component
=====================================

MercadoPago Payment Methods Logos, Sprites and CSS sorted by countries and sizes.

## Usage

For default size logos, just copy the css file for each country ([1](#guidelines-and-good-practices)) from the `dist` folder into your project and add them to your css bundles ([2](#guidelines-and-good-practices)).

In case you need a bigger size, or both sizes, you need to generate the custom files following the [Development setup](#development-setup) and [File generation](#file-generation) instructions.

## Development setup

1. Install [Git](http://git-scm.com/) and [NodeJS](http://nodejs.org/).

2. Open your terminal and clone `mercadolibre/payment-methods-component` by running:

        $ git clone git@github.com:mercadolibre/payment-methods-component.git

3. Now go to the project's folder:

        $ cd payment-methods-component

4. Install its dependencies:

        $ npm install

5. Install `grunt-cli`:

        $ npm install grunt-cli -g

## File generation

You can generate a file by country and by size using Grunt commands:

Ex: payment methods for Argentina with the default size:

    grunt build --country=ar

Ex: Payment methods for Argentina and large size:

    grunt build --country=ar --size=large

Ex: Payment methods for Argentina with both default and large size:

    grunt build --country=ar --size=defaul,large


You'll find the generated files in the `build` folder.

### Country List

- ar (Argentina)
- br (Brazil)
- mx (Mexico)
- ve (Venezuela)
- co (Colombia)
- cl (Chile)

### Size Lists

- default 
- large


## HTML Markup

- Each logo as its own class with the prefix `paymentmethod-`. Por example:

    ```
    paymentmethod-visa
    ```

- You can use them in any element. 
  
    ```html
    <!-- Unordered List -->
    <ul>
        <li class="paymentmethod-visa">Visa</li>
        <li class="paymentmethod-master">Mastercard</li>
        <li class="paymentmethod-amex">American Express</li>
    </ul>
    ```

    ```html
    <!-- Span -->
    <span class="paymentmethod-visa">Visa</span>
    ```

    ```html
    <!-- With Inline Text -->
    <p>
        <span class="paymentmethod-visa">Visa</span> terminada en 1234
    </p>
    ```

- Extend the size for large logos using the `paymentmethod-large` class:
    
    ```html
    <!-- This is a large logo -->
    <span class="paymentmethod-visa paymentmethod-large">Visa</span>
    ```

- Each payment method class uses the id field from the [MercadoPago Payment Methods API](https://api.mercadolibre.com/sites/MLA/payment_methods), so you can use variables to be able to use this service and load the logos dinamically.

     ```html
    <li class="paymentmethod-${id}">${name}</li>
    ```

## Guidelines and good practices

1. Use one file per country. Only load the component for that country.

2. Add it to your own bundles, don't make an extra request for it.


## Roadmap

Stuff that are coming on future versions:

- Retina Display Support
- Chile Logos
- A better demo
- Style guide for logo grouping on some countries
- Generic payment type logos

## Maintained by

- Gastón André (gaston.andre@mercadolibre.com)
- Ivan Pianciola (ivan.pianciola@mercadolibre.com)
- Adolfo Ramos (adolfo.ramos@mercadoibre.com)

## Thanks to

- Nati Devalle (@taly) 
- Guille Paz (@pazguille)

## Credits

![MercadoLibre](http://secure.mlstatic.com/org-img/chico/img/logo-mercadolibre-new.png)

## License
Licensed under the MIT license.

Copyright (c) 2014 [MercadoLibre](http://github.com/mercadolibre).

