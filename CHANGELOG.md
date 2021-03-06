changelog
=========

## 0.5
- a migrations system has been added, closing [#3](https://github.com/thedodd/wither/issues/3) & [#4](https://github.com/thedodd/wither/issues/4). The important part of this feature set is the `IntervalMigration` type.
- `Model::sync` has received some updates. It now synchronizes a model's indexes as well as its migrations.
- reexports of `bson::Document` & `mongodb::coll::options::FindOptions` have been removed. They must be vestiges of my early development on this crate.
- now testing all builds against MongoDB 3.2.x & 3.4.x. Will add 3.6.x when it is available on hub.docker.com.

#### 0.5.1
- updating create dependencies. No expected backwards incompatibilities from this.
- added some notes to the documentation on how to integrate this crate's logging.
- added MongoDB 3.6.x to the test matrix & update patch versions of existing versions in test matrix.

#### 0.5.2
This is an important release which implements a workaround for [a bug reported against the mongodb lib](https://github.com/mongodb-labs/mongo-rust-driver-prototype/issues/251). The bug was causing model syncing to fail for new models.
- a workaround was implemented for the above mentioned bug.
- a few `doc!` usages were updated to use `:` as opposed to `=>` for key/val delimiter.

##### backwards incompatibilities
- `Model::sync` no longer panics. It will now return a `Result`, offering users a greater level of control on behavior.

## 0.4
- adds `Model.update`.

## 0.3
- adds `Model::count`.

## 0.2
- adopts usage of `associated constants` for `Model`. Thus, `Model::collection_name()` has been replaced by the associated constant `Model::COLLECTION_NAME` and is required when adopting the `Model` trait for your types.
- adds an actual implementation for `Model::find`.

###### backwards incompatibilities
- `Model::collection_name` has been replaced with `Model::COLLECTION_NAME`.

#### 0.2.1
- no code changes here, just updating some docs & badge links.

## 0.1
Initial release.
