# swift-identities

Use this package when your models need identifiers that the compiler keeps apart, so a user's ID can't be passed where an order's ID belongs. Start from `Identity.ID`, tagged with the model type and holding any raw value, often an `Identity.UUID`. If you only need UUIDs and no tagging, use swift-uuids.

## Laws

- `Identity.UUID.random()` makes a version 4 UUID with the RFC 4122 variant, from the platform's secure random generator.
- An `Identity.UUID` prints as lowercase hex in the hyphenated 8-4-4-4-12 form, and that text parses back to the same value.
- Two IDs are equal exactly when their raw values are equal. The tag adds nothing at runtime.
