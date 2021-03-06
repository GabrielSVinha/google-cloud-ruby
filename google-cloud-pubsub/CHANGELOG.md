# Release History

### 0.27.0 / 2017-08-10

This is a major release that offers new functionality. It adds the ability to asynchronously publish batches of messages when a threshold is met (batch message count, total batch size, batch age). It also adds the ability to receive and acknowledge messages via multiple streams.

* Publishing Messages Asynchronously
  * `Topic#publish_async` and `AsyncPublisher` added
  * `AsyncPublisher` can be stopped
  * `PublishResult` object is yielded from `Topic#publish_async`
* Subscriber Streaming Messages
  * `Subscription#listen` changed to return a `Subscriber` object
  * `Subscriber` can open multiple streams to pull messages
  * `Subscriber` must be started to begin streaming messages
  * `Subscriber` can be stopped
  * `Subscriber`'s received messages are leased until acknowledged or rejected
* Other Additions
  * `ReceivedMessage#reject!` method added (aliased as `nack!` and `ignore!`)
  * `Message#published_at` attribute was added
* Removals
  * `Project#publish` method has been removed
  * `Project#subscribe` method has been removed
  * `Project#topic` method argument `autocreate` was removed
  * `Subscription#pull` method argument `autoack` was removed
  * `Subscription#wait_for_messages` method argument `autoack` was removed

### 0.26.0 / 2017-07-11

* Update GAPIC configuration to exclude `UNAVAILABLE` errors from automatic retry.
* Update initialization to raise a better error if project ID is not specified.

### 0.25.0 / 2017-06-01

* Add Snapshot and Subscription#seek.
* Add Subscription#retain_acked and Subscription#retention.
* Update gem spec homepage links.
* Remove memoization of Policy.
* Remove force parameter from Subscription#policy and Topic#policy.
* Remove Policy#deep_dup.
* Configure gRPC max_send_message_length and max_receive_message_length
to accommodate max message size > 4 MB.

### 0.24.0 / 2017-03-31

* Updated documentation
* Updated retry configuration for pull requests
* Automatic retry on `UNAVAILABLE` errors

### 0.23.2 / 2017-03-03

* No public API changes.
* Update GRPC header value sent to the Pub/Sub API.

### 0.23.1 / 2017-03-01

* No public API changes.
* Update GRPC header value sent to the Pub/Sub API.
* Low level API adds new Protobuf types and GAPIC methods.

### 0.23.0 / 2017-02-21

* Add emulator_host parameter
* Fix GRPC retry bug
* The client_config data structure has replaced retry_codes/retry_codes_def with retry_codes
* Update GRPC/Protobuf/GAX dependencies

### 0.22.0 / 2017-01-26

* Change class names in low-level API (GAPIC)
* Change method parameters in low-level API (GAPIC)
* Add LICENSE to package.

### 0.21.0 / 2016-10-20

* New service constructor Google::Cloud::Pubsub.new
* New constructor argument client_config

### 0.20.1 / 2016-09-02

* Fix an issue with the GRPC client and forked sub-processes

### 0.20.0 / 2016-08-26

This gem contains the Google Cloud Pub/Sub service implementation for the `google-cloud` gem. The `google-cloud` gem replaces the old `gcloud` gem. Legacy code can continue to use the `gcloud` gem.

* Namespace is now `Google::Cloud`
* The `google-cloud` gem is now an umbrella package for individual gems
