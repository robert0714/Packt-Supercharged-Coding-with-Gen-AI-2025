# 2 Your Quickstart Guide to OpenAI API
## Introducing OpenAI API
The Chat service by OpenAI is designed for conversational interactions with the LLM where the conversation uses three types of prompt roles – user, system, and assistant:
* **User prompts** represent an end user of the system such as a ChatGPT user, and resemble prompts we feed into ChatGPT, such as `Tell me about the Fibonacci sequence`.
* **Assistant prompts** represent the model output through the conversation and resemble answers we will get back from ChatGPT, such as `The Fibonacci sequence is a series of numbers where each number is the sum of the two preceding ones`.
* **System prompts** define the guidelines of the assistant behavior through the conversation, such as `You are a helpful programming instructor`.

## OpenAI API through a RESTful HTTP request
The OpenAI API services are accessed via RESTful HTTP requests, a communication protocol based on the principles of Representational State Transfer (REST) architecture, and using the HyperText Transfer Protocol (HTTP). RESTful HTTP provides a standardized way to send and retrieve data from servers over the internet. A request to OpenAI API includes four key components:

* **Endpoint**: The URL specifying the service you are accessing, such as https://api.openai.com/v1/chat/completions for the Chat service
* **HTTP method**: The action to perform, such as POST for OpenAI Chat service requests, which sends data to the server
* **Headers**: Metadata about the request, including your API token, to authenticate and provide context for the request
* **Body**: The data payload containing details such as the LLM to use and the input prompts

# OpenAI API Python package installation
> If you require additional assistance in setting up your virtual environments, refer to the [*Appendix* for detailed instructions](../Appendix/README.md).

The `openai` Python package simplifies the process by abstracting complexities such as URL paths, retries, error handling, and authentication. This allows us to interact directly with Python objects, instead of manually constructing RESTful HTTP requests.

To install the `openai` package, run the following command in your terminal within your virtual environment:
```bash
(.venv) $ pip install openai
```
To verify that the openai package is installed correctly on your virtual environment, run the following command, which specifies the information of the package:
```bash
(.venv) $ pip show openai
```

## Understanding rate limits and usage restrictions for free and paid OpenAI accounts
We encourage you to learn about your account’s API limits by navigating to the Settings section in the upper-left corner of your organization: https://platform.openai.com/settings/organization/limits.

## Further reading
To learn more about the topics that were covered in this chapter, take a look at the following resources:

1. OpenAI Platform home page: https://platform.openai.com
1. OpenAI API official documentation: https://platform.openai.com/docs/overview
1. OpenAI Pricing: https://openai.com/api/pricing/
1. OpenAI Rate Limits (General): https://platform.openai.com/docs/guides/rate-limits
1. OpenAI available models: https://platform.openai.com/docs/models/model-endpoint-compatibility
1. OpenAI individual rate limits: https://platform.openai.com/settings/organization/limits
1. The FizzBuzz wiki page: https://en.wikipedia.org/wiki/Fizz_buzz
1. The Two Sum Leet Code page: https://leetcode.com/problems/two-sum/description/