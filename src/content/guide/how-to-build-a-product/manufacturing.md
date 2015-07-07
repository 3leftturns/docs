---
title: Manufacturing, programming, and testing
columns: two
template: guide.hbs
order: 4
---

##OUTLINE

####1. Purchasing Particle hardware at volume
  - Buying from us vs. buying from module manufacturers
  - **Allow enough lead time**. We do not normally keep production quantities of hardware in inventory.  We need 8-12 weeks.
  - **Importing things into China**. This is a whole thing.  Think about it, be ready for it. Import licenses vs. freight forwarders vs. rebates.

####2. Build (and send) us a developmental prototype!

####3. Certifications
  - Different kinds of products need different kinds of certifications.
  - PTCRB
  - FCC
  - CE
  - IC
  - RoHS

####4. Programming the device
  - Programming at the factory
  - Programming over-the-air upon first connect

####5. Provisioning the device
  - Modules bought from us vs. bought independently
  - Record your hardware identifiers (device ID, setup code) for record-keeping

####6. Testing
  - Methodology (100% testing vs. batch testing, targeted tests, happy path)
  - LED function
  - Wi-Fi connectivity
  - Happy path
  - Test rig resources

####7. Device tracking and serialization
  - Format
  - Setup codes

####Open questions
- [ ] If we sell reels of hardware to people, do they register them to their organization or us?
- [ ] If they don't buy hardware from us, how do they provision their devices?  What are the requirements for us to let something connect to our cloud?
- [ ] What documentation or resources do we need provide to people in order to help them through certification? Just paperwork? Test firmwares?
- [ ] Do they need to record or send us anything if we're the ones providing the modules?
- [ ] Do they need to record or send us anything if they're buying Particle modules from someone else?
- [ ] Do they need to record or send us anything if they're buying generic modules from someone else?
- [ ] What is the official standard we want to communicate for uniquely identifying products on the Particle platform?
- [ ] Is recording the setup code relevant to people who are going to rewrite over our Tinker firmware on the assembly line? Should we construct a mandatory "PRODUCT NAME_SETUP CODE" format for SoftAP on our platform?

####Things we need to build:
- [ ] Open source firmware for serialization / setup code?
- [ ] Manufacturing API for provisioning?

---




You've finished your hardware and software development. Your PCB is designed and tested; you've built your own web and mobile apps, and you've had a few beta customers successfully use products that you've built for them by hand. You've lined up a contract manufacturer (CM), and now you're ready to start manufacturing.

In most cases, manufacturing with Particle hardware is the same as manufacturing with any other hardware. However there are some things to keep in mind when you program and test your products, and some opportunities to consider since your product is connected to the internet.

### Purchasing modules at scale

TODO

(Basic story: contact sales@particle.io to place an order and submit a purchase order (PO))

### Programming/test jig

TODO

(Basic story: you'll need to consider how your device will be programmed/tested on the manufacturing line. Perhaps we could open source and link to our test hardware/software?)

### Programming during manufacturing vs. over the air

TODO

(Basic story: Highlight the tradeoffs; programming on the line is recommended)

### Testing on the manufacturing line

TODO

(Basic story: be sure to test your product's functionality, as well as all necessary component connections and the RF performance of the device. Also capture the device ID off the device if at all possible. Can we provide our test firmware application and instructions for using it?)

### Tracking and serializing your devices

TODO

(Basic story: Connected devices provide the opportunity to compare customer behavior across distribution channels *if* you track your hardware properly. Consider adding a unique serial number for each device and tracking the mapping between these serial numbers and the device IDs. Let's also provide instructions for how to extract the device ID and the 4-6 digit hash that's in the setup mode)
