# Local Development and Setup
### Prerequisites
 - Make sure you have php version 7.4 or higher
   - Run `php -v`
 - Brew may no longer support version 7.4 so to install try the following
    - Run `brew install shivammathur/php/php@7.4`

### 1) Checkout Repository
- To get the repository locally run the following
 - RUN `git clone https://github.com/fashionphile/email-to-cloud.git`

### 2) Run / Build Instance
 - While on the FPemail directory run following command to install packages 
   - Run `composer update`
 
### 4) Usage
- To connect to the lambda and SFMC you must be on a valid IP address (FP VPN)
  - Otherwise, you'll only get 403 responses
- Pass required data to SendEmail function and your data will be validated and email sent
- One of the best way to develop is with tests run `vendor/bin/phpunit` to run testing suit

### 5) Tests
- To run all tests RUN `vendor/bin/phpunit`


### 6) Example
$email = new \FPemail\SendEmail('asldkjf');
        $email->to('tanner.robertson@fashionphile.com', 322087);
        $data = [
                "sku__c" => "BD595034",
                "discount_tier__c" => "70",
                "shopping_bag_count__c" => "3",
                "item_discount_amount__c" => "20",
                "original_product_price__c" => "1600",
            ];
        $email->setData($data);
        $email->send();
