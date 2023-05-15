# credit_card_flutter

A Flutter package allows you to easily implement the Credit card's UI easily with the Card detection.

### Installing 

Add dependency to pubspec.yaml
Get the latest version in the 'Installing' tab on pub.dev
```
dependencies:
    flutter_credit_card: <latest_version>
```    
Import the package
```
import 'package:flutter_credit_card/flutter_credit_card.dart';
```
Adding CreditCardWidget
With required parameters

    CreditCardWidget(
      cardNumber: cardNumber,
      expiryDate: expiryDate,
      cardHolderName: cardHolderName,
      cvvCode: cvvCode,
      showBackView: isCvvFocused, //true when you want to show cvv(back) view
    ),
With optional parameters

    CreditCardWidget(
      cardNumber: cardNumber,
      expiryDate: expiryDate,
      cardHolderName: cardHolderName,
      cvvCode: cvvCode,
      showBackView: isCvvFocused,
      cardbgColor: Colors.black,
      glassmorphismConfig: Glassmorphism.defaultConfig(),
      backgroundImage: 'assets/card_bg.png',
      obscureCardNumber: true,
      obscureInitialCardNumber: false,
      obscureCardCvv: true,
      isHolderNameVisible: false,
      height: 175,
      textStyle: TextStyle(color: Colors.yellowAccent),
      width: MediaQuery.of(context).size.width,
      isChipVisible: true,
      isSwipeGestureEnabled: true,
      animationDuration: Duration(milliseconds: 1000),
      frontCardBorder: Border.all(color: Colors.grey),
      backCardBorder: Border.all(color: Colors.grey),
      customCardIcons: <CustomCardTypeImage>[
        CustomCardTypeImage(
          cardType: CardType.mastercard,
          cardImage: Image.asset(
            'assets/mastercard.png',
            height: 48,
            width: 48,
          ),
        ),
      ],
    ),
Glassmorphism UI

- Default configuration
```
    CreditCardWidget(
      glassmorphismConfig: Glassmorphism.defaultConfig(),
    );
```
- Custom configuration
```
    CreditCardWidget(
      glassmorphismConfig: Glassmorphism(
        blurX: 10.0,
        blurY: 10.0,
        gradient: LinearGradient(
          begin: Alignment.topLeft,
          end: Alignment.bottomRight,
          colors: <Color>[
            Colors.grey.withAlpha(20),
            Colors.white.withAlpha(20),
          ],
          stops: const <double>[
            0.3,
            0,
          ],
        ),
      ),
    ),
```
Adding CreditCardForm
```
    CreditCardForm(
      formKey: formKey, // Required 
      cardNumberKey: cardNumberKey,
      cvvCodeKey: cvvCodeKey,
      expiryDateKey: expiryDateKey,
      cardHolderKey: cardHolderKey,
      onCreditCardModelChange: (CreditCardModel data) {}, // Required
      themeColor: Colors.red,
      obscureCvv: true, 
      obscureNumber: true,
      isHolderNameVisible: true,
      isCardNumberVisible: true,
      isExpiryDateVisible: true,
      enableCvv: true,
      cardNumberValidator: (String? cardNumber){},
      expiryDateValidator: (String? expiryDate){},
      cvvValidator: (String? cvv){},
      cardHolderValidator: (String? cardHolderName){},
      onFormComplete: () {
      // callback to execute at the end of filling card data
      },
      cardNumberDecoration: const InputDecoration(
        border: OutlineInputBorder(),
        labelText: 'Number',
        hintText: 'XXXX XXXX XXXX XXXX',
      ),
      expiryDateDecoration: const InputDecoration(
        border: OutlineInputBorder(),
        labelText: 'Expired Date',
        hintText: 'XX/XX',
      ),
      cvvCodeDecoration: const InputDecoration(
        border: OutlineInputBorder(),
        labelText: 'CVV',
        hintText: 'XXX',
      ),
      cardHolderDecoration: const InputDecoration(
        border: OutlineInputBorder(),
        labelText: 'Card Holder',
      ),
    ),
```
## Developers
MIT License

Copyright (c) 2019 TecOrb Technologies

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
