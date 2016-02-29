A simple image to run DynamoDB in local forked from [modli/dynamodb](https://hub.docker.com/r/modli/dynamodb/).

The main differences from the original Dockerfile are:

- Use lightweight Java image rather than one based on Debian
- Put the `-port` option in the entry point as the `EXPOSE` has to be consistent
with this option
- Default command includes `-delayTransientStatuses` to better simulate the
behavior of the actual dynamodb as well as `-sharedDb` and
`-optimizeDbBeforeStartup`
- Getting the jar is done in a single `RUN`
