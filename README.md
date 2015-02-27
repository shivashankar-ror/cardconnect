# CardConnect

CardConnect API Ruby Wrapper

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'cardconnect'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install cardconnect

## Usage

For Rails in config/initializers/cardconnect.rb

NOTE: Merchant ID can also be passed in with params when building a request. If no ID is passed in then the request will use the ID from the configuration.

```ruby
CardConnect.configure do |config|
  config.merchant_id = '<merchant-id-number>'
  config.api_username = '<api user id>'
  config.api_password = '<api user password>'
  config.endpoint = 'https://url.goeshere.com:6443'
end
```

## Services

### Authorization Service

CardConnect documentation for this service can be found here: http://developer.cardconnect.com/cardconnect-api/#authorization-service

Example:

```ruby
service = CardConnect::Service::Authorization.new
service.build_request(params)
response = service.submit
```

### Capture Service

CardConnect documentation for this service can be found here: http://developer.cardconnect.com/cardconnect-api/#capture-service

Example:

```ruby
service = CardConnect::Service::Capture.new
service.build_request(params)
response = service.submit
```

### Void Service

CardConnect documentation for this service can be found here: http://developer.cardconnect.com/cardconnect-api/#void-service

Example:

```ruby
service = CardConnect::Service::Void.new
service.build_request(params)
response = service.submit
```

### Refund Service

CardConnect documentation for this service can be found here: http://developer.cardconnect.com/cardconnect-api/#refund-service

Example:

```ruby
service = CardConnect::Service::Refund.new
service.build_request(params)
response = service.submit
```

### Inquire Service

CardConnect documentation for this service can be found here: http://developer.cardconnect.com/cardconnect-api/#inquire-service

Example:

```ruby
service = CardConnect::Service::Inquire.new
service.build_request(params)
response = service.submit
```

### Settlement Status Service

CardConnect documentation for this service can be found here: http://developer.cardconnect.com/cardconnect-api/#settlement-status-service

Example:

```ruby
service = CardConnect::Service::SettlementStatus.new
service.build_request(params)
response = service.submit
```

### Deposit Service

CardConnect documentation for this service can be found here: http://developer.cardconnect.com/cardconnect-api/#deposit-service

Example:

```ruby
service = CardConnect::Service::Deposit.new
service.build_request(params)
response = service.submit
```

### Response Codes

http://developer.cardconnect.com/cardconnect-api/#response-codes

## To Do:

#### Authorization Service

* Support for custom descriptor fields
* Support for Card Present authorizations is untested
* Support 3D Secure processing

#### Capture Service

* Support for Level 3 data including items

#### Funding Service

* Funding Service needs to be implemented

#### Profile Service

* Profile Service needs to be implemented

## Contributing

1. Fork it ( https://github.com/mobilecause/cardconnect/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
