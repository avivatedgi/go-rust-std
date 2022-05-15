<!-- Code generated by gomarkdoc. DO NOT EDIT -->

# option

```go
import "github.com/avivatedgi/go-rust-std/option"
```

## Index

- [func MapOr[T any, U any](option Option[T], other U, f func(*T) U) U](<#func-mapor>)
- [func MapOrElse[T any, U any](option Option[T], def func() U, f func(*T) U) U](<#func-maporelse>)
- [type Option](<#type-option>)
  - [func Map[T any, U any](option Option[T], f func(*T) U) Option[U]](<#func-map>)
  - [func None[T any]() Option[T]](<#func-none>)
  - [func Some[T any](value T) Option[T]](<#func-some>)
  - [func (option Option[T]) Expect(message string) T](<#func-optiont-expect>)
  - [func (option Option[T]) IsNone() bool](<#func-optiont-isnone>)
  - [func (option Option[T]) IsSome() bool](<#func-optiont-issome>)
  - [func (option Option[T]) IsSomeWith(f func(*T) bool) bool](<#func-optiont-issomewith>)
  - [func (option Option[T]) Unwrap() T](<#func-optiont-unwrap>)
  - [func (option Option[T]) UnwrapOr(other T) T](<#func-optiont-unwrapor>)
  - [func (option Option[T]) UnwrapOrDefault() T](<#func-optiont-unwrapordefault>)
  - [func (option Option[T]) UnwrapOrElse(f func() T) T](<#func-optiont-unwraporelse>)


## func MapOr

```go
func MapOr[T any, U any](option Option[T], other U, f func(*T) U) U
```

Returns the provided default result \(if none\)\, or applies a function to the contained value \(if any\)\. This function is not a method of option because method must have no type parameter\. https://github.com/golang/go/issues/48793

## func MapOrElse

```go
func MapOrElse[T any, U any](option Option[T], def func() U, f func(*T) U) U
```

Computes a default function result \(if none\)\, or applies a different function to the contained value \(if any\)\. This function is not a method of option because method must have no type parameter\. https://github.com/golang/go/issues/48793

## type Option

This Option implementation is based on the one in the Rust's standart library \(https://doc.rust-lang.org/std/option/enum.Option.html\) The Option represents an optional value: every Option is either Some and contains a value\, or None\, and does not\.

```go
type Option[T any] struct {
    // contains filtered or unexported fields
}
```

### func Map

```go
func Map[T any, U any](option Option[T], f func(*T) U) Option[U]
```

Maps an Option\[T\] to Option\[U\] by applying a function to a contained value\. This function is not a method of option because method must have no type parameter\. https://github.com/golang/go/issues/48793

### func None

```go
func None[T any]() Option[T]
```

Return an Option containing no value\.

### func Some

```go
func Some[T any](value T) Option[T]
```

Return an Option containing the value \`value\`\.

### func \(Option\[T\]\) Expect

```go
func (option Option[T]) Expect(message string) T
```

Returns the contained Some value\, consuming the option value\. Panics if the value is a None with a custom panic message provided by message\.

### func \(Option\[T\]\) IsNone

```go
func (option Option[T]) IsNone() bool
```

Returns true if the option is a None value\.

### func \(Option\[T\]\) IsSome

```go
func (option Option[T]) IsSome() bool
```

Returns true if the option is a Some value\.

### func \(Option\[T\]\) IsSomeWith

```go
func (option Option[T]) IsSomeWith(f func(*T) bool) bool
```

Returns true if the option is a Some wrapping a value matching the predicate\.

### func \(Option\[T\]\) Unwrap

```go
func (option Option[T]) Unwrap() T
```

Returns the contained Some value\, consuming the option value\. Because this function may panic\, its use is generally discouraged\. Instead\, prefer to use pattern matching and handle the None case explicitly\, or call UnwrapOr\, UnwrapOrElse\, or UnwrapOrDefault\. Panics if the self value equals None\.

### func \(Option\[T\]\) UnwrapOr

```go
func (option Option[T]) UnwrapOr(other T) T
```

Returns the contained Some value or a provided default\.

### func \(Option\[T\]\) UnwrapOrDefault

```go
func (option Option[T]) UnwrapOrDefault() T
```

Returns the contained Some value or a default\. Consumes the self argument then\, if Some\, returns the contained value\, otherwise if None\, returns the default value for that type\.

### func \(Option\[T\]\) UnwrapOrElse

```go
func (option Option[T]) UnwrapOrElse(f func() T) T
```

Returns the contained Some value or computes it from a closure\.



Generated by [gomarkdoc](<https://github.com/princjef/gomarkdoc>)