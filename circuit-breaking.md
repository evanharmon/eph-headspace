# CIRCUIT BREAKING
Circuit breaker pattern, which stops the client from waiting needlessly for an
unresponsive service. If the error rate for a service exceeds a specified
threshold, it turns off the endpoint/service for a period of time
