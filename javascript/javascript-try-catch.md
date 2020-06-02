# JAVASCRIPT TRY CATCH

## Correct Error Handling
```
exports.createMetadata = function* (settings) {
    try {
        var data = yield metadataJSON(settings);
        var xml  = yield exports.jsToXml(data);
    }
    catch (err) {
        debug("error creating metadata", err);
        return err;
    }

    if (!xml) {
        debug("Error creating metadata");
        return false;
    }

    return xml;
};
```

## Scenario 1:
Calling createMetadata() directly, the error will be returned and the catch
block debug message will fire

## Scenario 2:
Another function calls createMetadata() in another try/catch block, then the if
statement returns false and uses that debug message

# Try / Catch Wrapper
```
const tryCatch = (identifier, fn, ...args) => {
  logger.info({ event: `${identifier} Resolver` }, `args: ${args}`);
  try {
    return fn(...args);
  } catch (e) {
    logger.error({ event: `${identifier} Resolve Failed` }, `args: ${args}`);
    throw new Error(e);
  }
};
```
