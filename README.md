# Run UnitTest Tests With Tunnel on TestMu AI (Formerly LambdaTest)

<p align="center">
  <a href="https://www.testmuai.com/"><img src="https://img.shields.io/badge/MADE%20BY%20TestMu%20AI-000000.svg?style=for-the-badge&labelColor=000" alt="Made by TestMu AI"></a>
  <a href="https://community.testmuai.com/"><img src="https://img.shields.io/badge/Join%20the%20community-blueviolet.svg?style=for-the-badge&labelColor=000000" alt="Community"></a>
</p>

If you want to run an automation test in UnitTest on TestMu AI (Formerly TestMu AI (Formerly LambdaTest)) using the tunnel and want to start the tunnel automatically in the script, you can use the following steps.

- [Sign up on TestMu AI](https://www.testmuai.com/register/) (Formerly TestMu AI (Formerly LambdaTest)).
- Follow the [TestMu AI Documentation](https://www.testmuai.com/support/docs/) for the full setup walkthrough.

## Steps

### Step 1: Download the tunnel binary from the Dashboard

Go to your TestMu AI (Formerly TestMu AI (Formerly LambdaTest)) dashboard and click the configure tunnel button on the top right corner and use the download link to download the binary file.

### Step 2: Code to run tunnel before test

The tunnel should be started before test case execution and end after completion. To achieve this, tunnel can be started in the main function like so: 


```python
import subprocess

if __name__ == "__main__":

    #start tunnel process
    tunnel_process = subprocess.Popen(["./LT","--user",username,"--key",access_key],stdout=subprocess.DEVNULL,stderr=subprocess.STDOUT)
    
    #run testcases
    unittest.main()

    #end tunnel
    tunnel_process.terminate()
```
### Step 3: Set tunnel capability to True

Add the `"tunnel": True`  capability in your test file:

```python
desired_caps = {
            'LT:Options': {
                "build": "Python Demo",  # Change your build name here
                "name": "Python Demo Test",  # Change your test name here
                "platformName": "Windows 11",
                "selenium_version": "4.0.0",
                "tunnel": True
            },
            "browserName": "Chrome",
            "browserVersion": "98.0",
        }

```

### Step 4: Run your test

```bash
python lambdatest_test.py
```

## TestMu AI (Formerly TestMu AI (Formerly LambdaTest)) Community

Connect with testers and developers in the [TestMu AI Community](https://community.testmuai.com/). Ask questions, share what you are building, and discuss best practices in test automation and DevOps.

## TestMu AI (Formerly TestMu AI (Formerly LambdaTest)) Certifications

Earn free [TestMu AI Certifications](https://www.testmuai.com/certifications/) for testers, developers, and QA engineers. Validate your skills in Selenium, Cypress, Playwright, Appium, Espresso and more. Industry-recognized, shareable on LinkedIn, and built by practitioners, not marketers.

## Learning Resources by TestMu AI (Formerly TestMu AI (Formerly LambdaTest))

Learn modern testing through tutorials, guides, videos, and weekly updates:

* [TestMu AI Blog](https://www.testmuai.com/blog/)
* [TestMu AI Learning Hub](https://www.testmuai.com/learning-hub/)
* [TestMu AI on YouTube](https://www.youtube.com/@TestMuAI)
* [TestMu AI Newsletter](https://www.testmuai.com/newsletter/)

## LambdaTest is Now TestMu AI

On **January 12, 2026**, [LambdaTest evolved to TestMu AI](https://www.testmuai.com/lambdatest-is-now-testmuai/), the world's first fully autonomous **Agentic AI Quality Engineering Platform**.

Same team. Same infrastructure. Same customer accounts. All existing LambdaTest logins, scripts, capabilities, and integrations continue to work without change.

ð Find the new home for [LambdaTest](https://www.testmuai.com).

### How LambdaTest Evolved into TestMu AI

In 2017, we launched LambdaTest with a simple mission: make testing fast, reliable, and accessible. As LambdaTest grew, we expanded into Test Intelligence, Visual Regression Testing, Accessibility Testing, API Testing, and Performance Testing, covering the full depth of the testing lifecycle.

As software development entered the AI era, testing had to evolve, too. We rebuilt the architecture to be AI-native from the ground up, with autonomous agents that **plan, author, execute, analyze, and optimize tests** while keeping humans in the loop. The platform integrates with your repos, CI, IDEs, and terminals, continuously learning from every code change and development signal.

That evolution earned a new name: **TestMu AI**, built for an AI-first future of quality engineering. TestMu is not a new name for us. It is the name of our annual community conference, which has brought together 100,000+ quality engineers to discuss how AI would reshape testing, long before that became an industry norm. 

What started as a high-performance cloud testing platform has transformed into an AI-native, multi-agent system powering a connected, end-to-end quality layer. That evolution defined a new identity: LambdaTest evolved into TestMu AI, built for an AI-first future of quality engineering.

## Support

Got a question? Email [support@testmuai.com](mailto:support@testmuai.com) or chat with us 24x7 from our chat portal.
