# Microsoft Foundry AI Deployment & Guardrail Testing

**Technologies:** Microsoft Azure · Microsoft Foundry · GPT-5 mini · Python · OpenAI SDK · AI Safety Testing

## Project Overview

This project demonstrates the deployment and functional testing of a GPT-5 mini model in Microsoft Foundry. A Python client was used to send prompts to the deployed model API and record test outcomes.

The project evaluates normal model functionality and the behavior of configured content-filtering controls against a controlled jailbreak attempt.

## Architecture

User → Python Test Client → Microsoft Foundry Model Deployment → Model Response / Content Filtering → JSON Test Report

## Objectives

- Deploy an AI model in Microsoft Foundry.
- Integrate the deployed model through a Python API client.
- Validate responses to benign prompts.
- Test whether a jailbreak attempt triggers content filtering.
- Record test outcomes for technical review.

## Implementation

1. Created a Microsoft Foundry project.
2. Deployed the GPT-5 mini model.
3. Configured Python API access using environment variables.
4. Submitted a benign Azure networking prompt.
5. Submitted a controlled jailbreak test prompt.
6. Recorded timestamps, outcomes, and sanitized response details in JSON.

## Test Results

| Test | Observed result | Status |
|---|---|---|
| Benign prompt | Relevant Azure networking response received | PASS — initial functional test |
| Jailbreak attempt | API returned `400 content_filter`; jailbreak was detected and filtered | PASS |
| Full response capture | Saved benign response appeared truncated | Follow-up required |

## Security Findings

The tested benign prompt received a response, while the jailbreak attempt was explicitly blocked by Azure's content-filtering control.

These results demonstrate initial functional and guardrail validation. They do not prove resistance to all prompt-injection attacks or establish comprehensive security assurance.

## Skills Demonstrated

- Azure AI resource deployment
- Microsoft Foundry model management
- Python API integration
- Environment-based credential management
- AI safety and guardrail testing
- JSON test reporting
- Security validation and technical documentation

## Future Improvements

- Add automated assertions and repeatable test cases.
- Validate full response capture and benign-prompt quality.
- Test additional prompt-injection scenarios.
- Verify API authentication and unauthorized-access handling.
- Expand test coverage and document false-positive results.
- Add sanitized deployment screenshots and execution evidence.

## Security Notice

Credentials, API keys, access tokens, and other secrets must never be committed to this repository. Use environment variables or an approved secret-management service.

## Project Status

Initial model deployment and two prompt tests completed. Additional API, response-quality, and security validation remain planned.
# microsoft-foundry-guardrail-testing
Microsoft Foundry GPT-5 mini deployment, Python API integration, and AI guardrail validation.
