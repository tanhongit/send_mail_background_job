# Welcome to Rails 6 Send Mail Backgtound Job with gem sidekiq

The Rails 6  Send Mail Backgtound Job is a small task for everyone to practice more when programming with Ruby on Rails.

We will use gem sidekiq to perform this task.

## Support for me
Support this project :stuck_out_tongue_winking_eye: :pray:
<p align="center">
    <a href="https://www.paypal.me/tanhongit" target="_blank"><img src="https://img.shields.io/badge/Donate-PayPal-green.svg" data-origin="https://img.shields.io/badge/Donate-PayPal-green.svg" alt="PayPal buymeacoffee TanHongIT"></a>
</p>

# 1. Technology
- Ruby on Rails

# 2. Configuration requirements
We are going to build the web application using:
- Rails 6.0.3.2
- Ruby 2.7.1

# 4. What is background Job
Since you already know the call to your Application will be slow, you want it to happen in a background job, so that users can see the confirmation message in their browser immediately without having to wait for the charge to actually happen. To do this, you must create an Active Job class, implement that class to call charge!(), and then add code to the controller to execute this job. The flow looks like the following figure.

![Image](https://imgur.com/Ns3P04e.png)

# 5. Demo

![Image](https://imgur.com/xON93Xa.png)
