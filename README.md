# Research Notes

> **Disclaimer:** The information below is based on research and may contain inaccuracies.

![Bee Image](./img/bee.png)

## Problem

- Having one large LLM can lead to latency when integrating into an application. Users might also want to use their own internal data or fine-tune the model to meet specific requirements.
- Certain teams may require specific tuning, such as additional legal training and regular updates.
- Updating an LLM with the latest data is a significant task. With vendor lock-in, users must wait until the vendor updates their models. This can be problematic, especially for sectors that require daily updates with new data, such as the financial sector.

## Solution

- Build a platform that allows teams to bring their own models and fine-tuned datasets. This platform should facilitate easy integration of these models into the larger 'Hive model'.
- Allow LLMs to be compartmentalized into smaller LLMs, similar to a microservice architecture (feasibility of this approach is uncertain). This could potentially lead to better and more accurate results, and reduced latency.
- Implement a 'dictator' service that sits above the microLLMs. This service would determine which model is best suited for the problem or question asked. For instance, if a user asks about a law case from 1880, the micro Law LLM would be selected to handle the response.

## Theory

If we have multiple specialist LLMs, they might outperform larger LLM models. The MicroLLMs can be seen as specialists and experts in their areas, who are called upon by the 'dictator' when a question matches their skillset.