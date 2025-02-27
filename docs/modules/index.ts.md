---
title: index.ts
nav_order: 8
parent: Modules
---

## index overview

Added in v1.0.0

---

<h2 class="text-delta">Table of contents</h2>

- [Codec](#codec)
  - [Decoder (interface)](#decoder-interface)
  - [Encoder (interface)](#encoder-interface)
  - [InputOf (type alias)](#inputof-type-alias)
  - [OutputOf (type alias)](#outputof-type-alias)
  - [Type (class)](#type-class)
    - [pipe (method)](#pipe-method)
    - [asDecoder (method)](#asdecoder-method)
    - [asEncoder (method)](#asencoder-method)
    - [decode (method)](#decode-method)
    - [\_A (property)](#_a-property)
    - [\_O (property)](#_o-property)
    - [\_I (property)](#_i-property)
  - [TypeOf (type alias)](#typeof-type-alias)
- [Decode error](#decode-error)
  - [Context (interface)](#context-interface)
  - [ContextEntry (interface)](#contextentry-interface)
  - [Errors (interface)](#errors-interface)
  - [Validation (type alias)](#validation-type-alias)
  - [ValidationError (interface)](#validationerror-interface)
  - [failure](#failure)
  - [failures](#failures)
  - [success](#success)
- [combinators](#combinators)
  - [array](#array)
  - [brand](#brand)
  - [exact](#exact)
  - [intersection](#intersection)
  - [partial](#partial)
  - [readonly](#readonly)
  - [readonlyArray](#readonlyarray)
  - [record](#record)
  - [recursion](#recursion)
  - [refinement](#refinement)
  - [strict](#strict)
  - [tuple](#tuple)
  - [type](#type)
  - [union](#union)
  - [~~alias~~](#alias)
  - [~~clean~~](#clean)
  - [~~dictionary~~](#dictionary)
  - [~~interface~~](#interface)
  - [~~taggedUnion~~](#taggedunion)
- [constructors](#constructors)
  - [keyof](#keyof)
  - [literal](#literal)
- [primitives](#primitives)
  - [Function](#function)
  - [Int](#int)
  - [Integer](#integer)
  - [UnknownArray](#unknownarray)
  - [UnknownRecord](#unknownrecord)
  - [any](#any)
  - [bigint](#bigint)
  - [boolean](#boolean)
  - [never](#never)
  - [null](#null)
  - [nullType](#nulltype)
  - [number](#number)
  - [string](#string)
  - [undefined](#undefined)
  - [unknown](#unknown)
  - [void](#void)
  - [voidType](#voidtype)
  - [~~Array~~](#array)
  - [~~Dictionary~~](#dictionary)
  - [~~object~~](#object)
- [utils](#utils)
  - [Any (interface)](#any-interface)
  - [AnyArrayType (class)](#anyarraytype-class)
    - [\_tag (property)](#_tag-property)
  - [AnyC (interface)](#anyc-interface)
  - [AnyDictionaryType (class)](#anydictionarytype-class)
    - [\_tag (property)](#_tag-property-1)
  - [AnyProps (interface)](#anyprops-interface)
  - [AnyType (class)](#anytype-class)
    - [\_tag (property)](#_tag-property-2)
  - [ArrayC (interface)](#arrayc-interface)
  - [ArrayType (class)](#arraytype-class)
    - [\_tag (property)](#_tag-property-3)
  - [BigIntC (interface)](#bigintc-interface)
  - [BigIntType (class)](#biginttype-class)
    - [\_tag (property)](#_tag-property-4)
  - [BooleanC (interface)](#booleanc-interface)
  - [BooleanType (class)](#booleantype-class)
    - [\_tag (property)](#_tag-property-5)
  - [Brand (interface)](#brand-interface)
  - [BrandC (interface)](#brandc-interface)
  - [Branded (type alias)](#branded-type-alias)
  - [Decode (type alias)](#decode-type-alias)
  - [DictionaryType (class)](#dictionarytype-class)
    - [\_tag (property)](#_tag-property-6)
  - [Encode (type alias)](#encode-type-alias)
  - [ExactC (interface)](#exactc-interface)
  - [ExactType (class)](#exacttype-class)
    - [\_tag (property)](#_tag-property-7)
  - [FunctionC (interface)](#functionc-interface)
  - [FunctionType (class)](#functiontype-class)
    - [\_tag (property)](#_tag-property-8)
  - [HasProps (type alias)](#hasprops-type-alias)
  - [HasPropsIntersection (interface)](#haspropsintersection-interface)
  - [HasPropsReadonly (interface)](#haspropsreadonly-interface)
  - [HasPropsRefinement (interface)](#haspropsrefinement-interface)
  - [Int (type alias)](#int-type-alias)
  - [IntBrand (interface)](#intbrand-interface)
  - [InterfaceType (class)](#interfacetype-class)
    - [\_tag (property)](#_tag-property-9)
  - [IntersectionC (interface)](#intersectionc-interface)
  - [IntersectionType (class)](#intersectiontype-class)
    - [\_tag (property)](#_tag-property-10)
  - [Is (type alias)](#is-type-alias)
  - [KeyofC (interface)](#keyofc-interface)
  - [KeyofType (class)](#keyoftype-class)
    - [\_tag (property)](#_tag-property-11)
  - [LiteralC (interface)](#literalc-interface)
  - [LiteralType (class)](#literaltype-class)
    - [\_tag (property)](#_tag-property-12)
  - [Mixed (interface)](#mixed-interface)
  - [NeverC (interface)](#neverc-interface)
  - [NeverType (class)](#nevertype-class)
    - [\_tag (property)](#_tag-property-13)
  - [NullC (interface)](#nullc-interface)
  - [NullType (class)](#nulltype-class)
    - [\_tag (property)](#_tag-property-14)
  - [NumberC (interface)](#numberc-interface)
  - [NumberType (class)](#numbertype-class)
    - [\_tag (property)](#_tag-property-15)
  - [OutputOfDictionary (type alias)](#outputofdictionary-type-alias)
  - [OutputOfPartialProps (type alias)](#outputofpartialprops-type-alias)
  - [OutputOfProps (type alias)](#outputofprops-type-alias)
  - [PartialC (interface)](#partialc-interface)
  - [PartialType (class)](#partialtype-class)
    - [\_tag (property)](#_tag-property-16)
  - [Props (interface)](#props-interface)
  - [ReadonlyArrayC (interface)](#readonlyarrayc-interface)
  - [ReadonlyArrayType (class)](#readonlyarraytype-class)
    - [\_tag (property)](#_tag-property-17)
  - [ReadonlyC (interface)](#readonlyc-interface)
  - [ReadonlyType (class)](#readonlytype-class)
    - [\_tag (property)](#_tag-property-18)
  - [RecordC (interface)](#recordc-interface)
  - [RecursiveType (class)](#recursivetype-class)
    - [\_tag (property)](#_tag-property-19)
    - [type (property)](#type-property)
  - [RefinementC (interface)](#refinementc-interface)
  - [RefinementType (class)](#refinementtype-class)
    - [\_tag (property)](#_tag-property-20)
  - [StringC (interface)](#stringc-interface)
  - [StringType (class)](#stringtype-class)
    - [\_tag (property)](#_tag-property-21)
  - [TupleC (interface)](#tuplec-interface)
  - [TupleType (class)](#tupletype-class)
    - [\_tag (property)](#_tag-property-22)
  - [TypeC (interface)](#typec-interface)
  - [TypeOfDictionary (type alias)](#typeofdictionary-type-alias)
  - [TypeOfPartialProps (type alias)](#typeofpartialprops-type-alias)
  - [TypeOfProps (type alias)](#typeofprops-type-alias)
  - [UndefinedC (interface)](#undefinedc-interface)
  - [UndefinedType (class)](#undefinedtype-class)
    - [\_tag (property)](#_tag-property-23)
  - [UnionC (interface)](#unionc-interface)
  - [UnionType (class)](#uniontype-class)
    - [\_tag (property)](#_tag-property-24)
  - [UnknownArrayC (interface)](#unknownarrayc-interface)
  - [UnknownC (interface)](#unknownc-interface)
  - [UnknownRecordC (interface)](#unknownrecordc-interface)
  - [UnknownType (class)](#unknowntype-class)
    - [\_tag (property)](#_tag-property-25)
  - [Validate (type alias)](#validate-type-alias)
  - [VoidC (interface)](#voidc-interface)
  - [VoidType (class)](#voidtype-class)
    - [\_tag (property)](#_tag-property-26)
  - [appendContext](#appendcontext)
  - [getContextEntry](#getcontextentry)
  - [getFunctionName](#getfunctionname)
  - [identity](#identity)
  - [~~Compact~~ (type alias)](#compact-type-alias)
  - [~~Exact~~ (type alias)](#exact-type-alias)
  - [~~ObjectC~~ (interface)](#objectc-interface)
  - [~~ObjectType~~ (class)](#objecttype-class)
    - [\_tag (property)](#_tag-property-27)
  - [~~PropsOf~~ (type alias)](#propsof-type-alias)
  - [~~StrictC~~ (interface)](#strictc-interface)
  - [~~StrictType~~ (class)](#stricttype-class)
    - [\_tag (property)](#_tag-property-28)
  - [~~TaggedExact~~ (interface)](#taggedexact-interface)
  - [~~TaggedIntersectionArgument~~ (type alias)](#taggedintersectionargument-type-alias)
  - [~~TaggedIntersection~~ (interface)](#taggedintersection-interface)
  - [~~TaggedProps~~ (type alias)](#taggedprops-type-alias)
  - [~~TaggedRefinement~~ (interface)](#taggedrefinement-interface)
  - [~~TaggedUnionC~~ (interface)](#taggedunionc-interface)
  - [~~TaggedUnionType~~ (class)](#taggeduniontype-class)
  - [~~TaggedUnion~~ (interface)](#taggedunion-interface)
  - [~~Tagged~~ (type alias)](#tagged-type-alias)
  - [~~getDefaultContext~~](#getdefaultcontext)
  - [~~getValidationError~~](#getvalidationerror)
  - [~~mixed~~ (type alias)](#mixed-type-alias)

---

# Codec

## Decoder (interface)

**Signature**

```ts
export interface Decoder<I, A> {
  readonly name: string
  readonly validate: Validate<I, A>
  readonly decode: Decode<I, A>
}
```

Added in v1.0.0

## Encoder (interface)

**Signature**

```ts
export interface Encoder<A, O> {
  readonly encode: Encode<A, O>
}
```

Added in v1.0.0

## InputOf (type alias)

**Signature**

```ts
export type InputOf<C extends Any> = C['_I']
```

Added in v1.0.0

## OutputOf (type alias)

**Signature**

```ts
export type OutputOf<C extends Any> = C['_O']
```

Added in v1.0.0

## Type (class)

**Signature**

```ts
export declare class Type<A, O, I> {
  constructor(
    /** a unique name for this codec */
    readonly name: string,
    /** a custom type guard */
    readonly is: Is<A>,
    /** succeeds if a value of type I can be decoded to a value of type A */
    readonly validate: Validate<I, A>,
    /** converts a value of type A to a value of type O */
    readonly encode: Encode<A, O>
  )
}
```

Added in v1.0.0

### pipe (method)

**Signature**

```ts
pipe<B, IB, A extends IB, OB extends A>(
    this: Type<A, O, I>,
    ab: Type<B, OB, IB>,
    name = ensure(this, () => `pipe(${this.name}, ${ab.name})`)
  ): Type<B, O, I>
```

Added in v1.0.0

### asDecoder (method)

**Signature**

```ts
asDecoder(): Decoder<I, A>
```

Added in v1.0.0

### asEncoder (method)

**Signature**

```ts
asEncoder(): Encoder<A, O>
```

Added in v1.0.0

### decode (method)

a version of `validate` with a default context

**Signature**

```ts
decode(i: I): Validation<A>
```

Added in v1.0.0

### \_A (property)

**Signature**

```ts
readonly _A: A
```

Added in v1.0.0

### \_O (property)

**Signature**

```ts
readonly _O: O
```

Added in v1.0.0

### \_I (property)

**Signature**

```ts
readonly _I: I
```

Added in v1.0.0

## TypeOf (type alias)

**Signature**

```ts
export type TypeOf<C extends Any> = C['_A']
```

Added in v1.0.0

# Decode error

## Context (interface)

**Signature**

```ts
export interface Context extends ReadonlyArray<ContextEntry> {}
```

Added in v1.0.0

## ContextEntry (interface)

**Signature**

```ts
export interface ContextEntry {
  readonly key: string
  readonly type: Decoder<any, any>
  /** the input data */
  readonly actual?: unknown
}
```

Added in v1.0.0

## Errors (interface)

**Signature**

```ts
export interface Errors extends Array<ValidationError> {}
```

Added in v1.0.0

## Validation (type alias)

**Signature**

```ts
export type Validation<A> = Either<Errors, A>
```

Added in v1.0.0

## ValidationError (interface)

**Signature**

```ts
export interface ValidationError {
  /** the offending (sub)value */
  readonly value: unknown
  /** where the error originated */
  readonly context: Context
  /** optional custom error message */
  readonly message?: string
}
```

Added in v1.0.0

## failure

**Signature**

```ts
export declare const failure: <T>(value: unknown, context: Context, message?: string | undefined) => Either<Errors, T>
```

Added in v1.0.0

## failures

**Signature**

```ts
export declare const failures: <T>(errors: Errors) => Either<Errors, T>
```

Added in v1.0.0

## success

**Signature**

```ts
export declare const success: <T>(value: T) => Either<Errors, T>
```

Added in v1.0.0

# combinators

## array

**Signature**

```ts
export declare function array<C extends Mixed>(item: C, name = ensure(item, () => `Array<${item.name}>`)): ArrayC<C>
```

Added in v1.0.0

## brand

**Signature**

```ts
export declare function brand<C extends Any, N extends string, B extends { readonly [K in N]: symbol }>(
  codec: C,
  predicate: Refinement<TypeOf<C>, Branded<TypeOf<C>, B>>,
  name: N
): BrandC<C, B>
```

Added in v1.8.1

## exact

Strips additional properties.

**Signature**

```ts
export declare function exact<C extends HasProps>(
  codec: C,
  name: string = ensure(codec, () => getExactTypeName(codec))
): ExactC<C>
```

Added in v1.1.0

## intersection

**Signature**

```ts
export declare function intersection<
  A extends Mixed,
  B extends Mixed,
  C extends Mixed,
  D extends Mixed,
  E extends Mixed
>(codecs: [A, B, C, D, E], name?: string): IntersectionC<[A, B, C, D, E]>
export declare function intersection<A extends Mixed, B extends Mixed, C extends Mixed, D extends Mixed>(
  codecs: [A, B, C, D],
  name?: string
): IntersectionC<[A, B, C, D]>
export declare function intersection<A extends Mixed, B extends Mixed, C extends Mixed>(
  codecs: [A, B, C],
  name?: string
): IntersectionC<[A, B, C]>
export declare function intersection<A extends Mixed, B extends Mixed>(
  codecs: [A, B],
  name?: string
): IntersectionC<[A, B]>
```

Added in v1.0.0

## partial

**Signature**

```ts
export declare function partial<P extends Props>(
  props: P,
  name: string = ensure(props, () => getPartialTypeName(getInterfaceTypeName(props)), partialPropsCache)
): PartialC<P>
```

Added in v1.0.0

## readonly

**Signature**

```ts
export declare function readonly<C extends Mixed>(
  codec: C,
  name = ensure(codec, () => `Readonly<${codec.name}>`)
): ReadonlyC<C>
```

Added in v1.0.0

## readonlyArray

**Signature**

```ts
export declare function readonlyArray<C extends Mixed>(
  item: C,
  name = ensure(item, () => `ReadonlyArray<${item.name}>`)
): ReadonlyArrayC<C>
```

Added in v1.0.0

## record

**Signature**

```ts
export declare function record<D extends Mixed, C extends Mixed>(domain: D, codomain: C, name?: string): RecordC<D, C>
```

Added in v1.7.1

## recursion

**Signature**

```ts
export declare function recursion<A, O = A, I = unknown, C extends Type<A, O, I> = Type<A, O, I>>(
  name: string,
  definition: (self: C) => C
): RecursiveType<C, A, O, I>
```

Added in v1.0.0

## refinement

**Signature**

```ts
export declare function refinement<C extends Any, B extends TypeOf<C>>(
  codec: C,
  refinement: Refinement<TypeOf<C>, B>,
  name?: string
): RefinementC<C, B>
export declare function refinement<C extends Any>(
  codec: C,
  predicate: Predicate<TypeOf<C>>,
  name?: string
): RefinementC<C>
```

Added in v1.0.0

## strict

Strips additional properties, equivalent to `exact(type(props))`.

**Signature**

```ts
export declare const strict: <P extends Props>(props: P, name?: string | undefined) => ExactC<TypeC<P>>
```

Added in v1.0.0

## tuple

**Signature**

```ts
export declare function tuple<A extends Mixed, B extends Mixed, C extends Mixed, D extends Mixed, E extends Mixed>(
  codecs: [A, B, C, D, E],
  name?: string
): TupleC<[A, B, C, D, E]>
export declare function tuple<A extends Mixed, B extends Mixed, C extends Mixed, D extends Mixed>(
  codecs: [A, B, C, D],
  name?: string
): TupleC<[A, B, C, D]>
export declare function tuple<A extends Mixed, B extends Mixed, C extends Mixed>(
  codecs: [A, B, C],
  name?: string
): TupleC<[A, B, C]>
export declare function tuple<A extends Mixed, B extends Mixed>(codecs: [A, B], name?: string): TupleC<[A, B]>
export declare function tuple<A extends Mixed>(codecs: [A], name?: string): TupleC<[A]>
```

Added in v1.0.0

## type

**Signature**

```ts
export declare function type<P extends Props>(
  props: P,
  name: string = ensure(props, () => getInterfaceTypeName(props), interfacePropsCache)
): TypeC<P>
```

Added in v1.0.0

## union

**Signature**

```ts
export declare function union<CS extends [Mixed, Mixed, ...Array<Mixed>]>(
  codecs: CS,
  name: string = getUnionName(codecs)
): UnionC<CS>
```

Added in v1.0.0

## ~~alias~~

Keeps the codec "kind".

**Signature**

```ts
export declare function alias<A, O, P, I>(
  codec: PartialType<P, A, O, I>
): <AA extends A, OO extends O = O, PP extends P = P, II extends I = I>() => PartialType<PP, AA, OO, II>
export declare function alias<A, O, P, I>(
  // tslint:disable-next-line: deprecation
  codec: StrictType<P, A, O, I>
): <AA extends A, OO extends O = O, PP extends P = P, II extends I = I>() => // tslint:disable-next-line: deprecation
StrictType<PP, AA, OO, II>
export declare function alias<A, O, P, I>(
  codec: InterfaceType<P, A, O, I>
): <AA extends A, OO extends O = O, PP extends P = P, II extends I = I>() => InterfaceType<PP, AA, OO, II>
```

Added in v1.1.0

## ~~clean~~

Drops the codec "kind".

**Signature**

```ts
export declare function clean<A, O = A, I = unknown>(codec: Type<A, O, I>): Type<A, O, I>
```

Added in v1.1.0

## ~~dictionary~~

Use `record` instead.

**Signature**

```ts
export declare const dictionary: typeof record
```

Added in v1.0.0

## ~~interface~~

Use `type` instead.

**Signature**

```ts
export declare const interface: typeof type
```

Added in v1.0.0

## ~~taggedUnion~~

Use `union` instead.

**Signature**

```ts
export declare const taggedUnion: <Tag extends string, CS extends [Mixed, Mixed, ...Mixed[]]>(
  tag: Tag,
  codecs: CS,
  name?: string
) => TaggedUnionC<Tag, CS>
```

Added in v1.3.0

# constructors

## keyof

**Signature**

```ts
export declare function keyof<D extends { [key: string]: unknown }>(
  keys: D,
  name: string = ensure(keys, () =>
    Object.keys(keys)
      .map((k) => JSON.stringify(k))
      .join(' | ')
  )
): KeyofC<D>
```

Added in v1.0.0

## literal

**Signature**

```ts
export declare function literal<V extends LiteralValue>(value: V, name: string = JSON.stringify(value)): LiteralC<V>
```

Added in v1.0.0

# primitives

## Function

**Signature**

```ts
export declare const Function: FunctionC
```

Added in v1.0.0

## Int

A branded codec representing an integer

**Signature**

```ts
export declare const Int: BrandC<NumberC, IntBrand>
```

Added in v1.8.1

## Integer

**Signature**

```ts
export declare const Integer: RefinementC<NumberC, number>
```

Added in v1.0.0

## UnknownArray

**Signature**

```ts
export declare const UnknownArray: UnknownArrayC
```

Added in v1.7.1

## UnknownRecord

**Signature**

```ts
export declare const UnknownRecord: UnknownRecordC
```

Added in v1.7.1

## any

**Signature**

```ts
export declare const any: AnyC
```

Added in v1.0.0

## bigint

**Signature**

```ts
export declare const bigint: BigIntC
```

Added in v2.1.0

## boolean

**Signature**

```ts
export declare const boolean: BooleanC
```

Added in v1.0.0

## never

**Signature**

```ts
export declare const never: NeverC
```

Added in v1.0.0

## null

**Signature**

```ts
export declare const null: NullC
```

Added in v1.0.0

## nullType

**Signature**

```ts
export declare const nullType: NullC
```

Added in v1.0.0

## number

**Signature**

```ts
export declare const number: NumberC
```

Added in v1.0.0

## string

**Signature**

```ts
export declare const string: StringC
```

Added in v1.0.0

## undefined

**Signature**

```ts
export declare const undefined: UndefinedC
```

Added in v1.0.0

## unknown

**Signature**

```ts
export declare const unknown: UnknownC
```

Added in v1.5.0

## void

**Signature**

```ts
export declare const void: VoidC
```

Added in v1.0.0

## voidType

**Signature**

```ts
export declare const voidType: VoidC
```

Added in v1.2.0

## ~~Array~~

Use `UnknownArray` instead.

**Signature**

```ts
export declare const Array: UnknownArrayC
```

Added in v1.0.0

## ~~Dictionary~~

Use `UnknownRecord` instead.

**Signature**

```ts
export declare const Dictionary: UnknownRecordC
```

Added in v1.0.0

## ~~object~~

Use `UnknownRecord` instead.

**Signature**

```ts
export declare const object: ObjectC
```

Added in v1.0.0

# utils

## Any (interface)

**Signature**

```ts
export interface Any extends Type<any, any, any> {}
```

Added in v1.0.0

## AnyArrayType (class)

**Signature**

```ts
export declare class AnyArrayType {
  constructor()
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "AnyArrayType"
```

Added in v1.0.0

## AnyC (interface)

**Signature**

```ts
export interface AnyC extends AnyType {}
```

Added in v1.5.3

## AnyDictionaryType (class)

**Signature**

```ts
export declare class AnyDictionaryType {
  constructor()
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "AnyDictionaryType"
```

Added in v1.0.0

## AnyProps (interface)

**Signature**

```ts
export interface AnyProps {
  [key: string]: Any
}
```

Added in v1.0.0

## AnyType (class)

**Signature**

```ts
export declare class AnyType {
  constructor()
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "AnyType"
```

Added in v1.0.0

## ArrayC (interface)

**Signature**

```ts
export interface ArrayC<C extends Mixed> extends ArrayType<C, Array<TypeOf<C>>, Array<OutputOf<C>>, unknown> {}
```

Added in v1.5.3

## ArrayType (class)

**Signature**

```ts
export declare class ArrayType<C, A, O, I> {
  constructor(
    name: string,
    is: ArrayType<C, A, O, I>['is'],
    validate: ArrayType<C, A, O, I>['validate'],
    encode: ArrayType<C, A, O, I>['encode'],
    readonly type: C
  )
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "ArrayType"
```

Added in v1.0.0

## BigIntC (interface)

**Signature**

```ts
export interface BigIntC extends BigIntType {}
```

Added in v2.1.0

## BigIntType (class)

**Signature**

```ts
export declare class BigIntType {
  constructor()
}
```

Added in v2.1.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "BigIntType"
```

Added in v1.0.0

## BooleanC (interface)

**Signature**

```ts
export interface BooleanC extends BooleanType {}
```

Added in v1.5.3

## BooleanType (class)

**Signature**

```ts
export declare class BooleanType {
  constructor()
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "BooleanType"
```

Added in v1.0.0

## Brand (interface)

**Signature**

```ts
export interface Brand<B> {
  readonly [_brand]: B
}
```

Added in v1.8.1

## BrandC (interface)

**Signature**

```ts
export interface BrandC<C extends Any, B> extends RefinementType<C, Branded<TypeOf<C>, B>, OutputOf<C>, InputOf<C>> {}
```

Added in v1.8.1

## Branded (type alias)

**Signature**

```ts
export type Branded<A, B> = A & Brand<B>
```

Added in v1.8.1

## Decode (type alias)

**Signature**

```ts
export type Decode<I, A> = (i: I) => Validation<A>
```

Added in v1.0.0

## DictionaryType (class)

**Signature**

```ts
export declare class DictionaryType<D, C, A, O, I> {
  constructor(
    name: string,
    is: DictionaryType<D, C, A, O, I>['is'],
    validate: DictionaryType<D, C, A, O, I>['validate'],
    encode: DictionaryType<D, C, A, O, I>['encode'],
    readonly domain: D,
    readonly codomain: C
  )
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "DictionaryType"
```

Added in v1.0.0

## Encode (type alias)

**Signature**

```ts
export type Encode<A, O> = (a: A) => O
```

Added in v1.0.0

## ExactC (interface)

**Signature**

```ts
export interface ExactC<C extends HasProps> extends ExactType<C, TypeOf<C>, OutputOf<C>, InputOf<C>> {}
```

Added in v1.5.3

## ExactType (class)

**Signature**

```ts
export declare class ExactType<C, A, O, I> {
  constructor(
    name: string,
    is: ExactType<C, A, O, I>['is'],
    validate: ExactType<C, A, O, I>['validate'],
    encode: ExactType<C, A, O, I>['encode'],
    readonly type: C
  )
}
```

Added in v1.1.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "ExactType"
```

Added in v1.0.0

## FunctionC (interface)

**Signature**

```ts
export interface FunctionC extends FunctionType {}
```

Added in v1.5.3

## FunctionType (class)

**Signature**

```ts
export declare class FunctionType {
  constructor()
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "FunctionType"
```

Added in v1.0.0

## HasProps (type alias)

**Signature**

```ts
export type HasProps =
  | HasPropsRefinement
  | HasPropsReadonly
  | HasPropsIntersection
  | InterfaceType<any, any, any, any>
  // tslint:disable-next-line: deprecation
  | StrictType<any, any, any, any>
  | PartialType<any, any, any, any>
```

Added in v1.1.0

## HasPropsIntersection (interface)

**Signature**

```ts
export interface HasPropsIntersection extends IntersectionType<Array<HasProps>, any, any, any> {}
```

Added in v1.1.0

## HasPropsReadonly (interface)

**Signature**

```ts
export interface HasPropsReadonly extends ReadonlyType<HasProps, any, any, any> {}
```

Added in v1.1.0

## HasPropsRefinement (interface)

**Signature**

```ts
export interface HasPropsRefinement extends RefinementType<HasProps, any, any, any> {}
```

Added in v1.1.0

## Int (type alias)

**Signature**

```ts
export type Int = Branded<number, IntBrand>
```

Added in v1.8.1

## IntBrand (interface)

**Signature**

```ts
export interface IntBrand {
  readonly Int: unique symbol
}
```

Added in v1.8.1

## InterfaceType (class)

**Signature**

```ts
export declare class InterfaceType<P, A, O, I> {
  constructor(
    name: string,
    is: InterfaceType<P, A, O, I>['is'],
    validate: InterfaceType<P, A, O, I>['validate'],
    encode: InterfaceType<P, A, O, I>['encode'],
    readonly props: P
  )
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "InterfaceType"
```

Added in v1.0.0

## IntersectionC (interface)

**Signature**

```ts
export interface IntersectionC<CS extends [Mixed, Mixed, ...Array<Mixed>]>
  extends IntersectionType<
    CS,
    CS extends { length: 2 }
      ? TypeOf<CS[0]> & TypeOf<CS[1]>
      : CS extends { length: 3 }
      ? TypeOf<CS[0]> & TypeOf<CS[1]> & TypeOf<CS[2]>
      : CS extends { length: 4 }
      ? TypeOf<CS[0]> & TypeOf<CS[1]> & TypeOf<CS[2]> & TypeOf<CS[3]>
      : CS extends { length: 5 }
      ? TypeOf<CS[0]> & TypeOf<CS[1]> & TypeOf<CS[2]> & TypeOf<CS[3]> & TypeOf<CS[4]>
      : unknown,
    CS extends { length: 2 }
      ? OutputOf<CS[0]> & OutputOf<CS[1]>
      : CS extends { length: 3 }
      ? OutputOf<CS[0]> & OutputOf<CS[1]> & OutputOf<CS[2]>
      : CS extends { length: 4 }
      ? OutputOf<CS[0]> & OutputOf<CS[1]> & OutputOf<CS[2]> & OutputOf<CS[3]>
      : CS extends { length: 5 }
      ? OutputOf<CS[0]> & OutputOf<CS[1]> & OutputOf<CS[2]> & OutputOf<CS[3]> & OutputOf<CS[4]>
      : unknown,
    unknown
  > {}
```

Added in v1.5.3

## IntersectionType (class)

**Signature**

```ts
export declare class IntersectionType<CS, A, O, I> {
  constructor(
    name: string,
    is: IntersectionType<CS, A, O, I>['is'],
    validate: IntersectionType<CS, A, O, I>['validate'],
    encode: IntersectionType<CS, A, O, I>['encode'],
    readonly types: CS
  )
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "IntersectionType"
```

Added in v1.0.0

## Is (type alias)

**Signature**

```ts
export type Is<A> = (u: unknown) => u is A
```

Added in v1.0.0

## KeyofC (interface)

**Signature**

```ts
export interface KeyofC<D extends { [key: string]: unknown }> extends KeyofType<D> {}
```

Added in v1.5.3

## KeyofType (class)

**Signature**

```ts
export declare class KeyofType<D> {
  constructor(
    name: string,
    is: KeyofType<D>['is'],
    validate: KeyofType<D>['validate'],
    encode: KeyofType<D>['encode'],
    readonly keys: D
  )
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "KeyofType"
```

Added in v1.0.0

## LiteralC (interface)

**Signature**

```ts
export interface LiteralC<V extends LiteralValue> extends LiteralType<V> {}
```

Added in v1.5.3

## LiteralType (class)

**Signature**

```ts
export declare class LiteralType<V> {
  constructor(
    name: string,
    is: LiteralType<V>['is'],
    validate: LiteralType<V>['validate'],
    encode: LiteralType<V>['encode'],
    readonly value: V
  )
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "LiteralType"
```

Added in v1.0.0

## Mixed (interface)

**Signature**

```ts
export interface Mixed extends Type<any, any, unknown> {}
```

Added in v1.0.0

## NeverC (interface)

**Signature**

```ts
export interface NeverC extends NeverType {}
```

Added in v1.5.3

## NeverType (class)

**Signature**

```ts
export declare class NeverType {
  constructor()
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "NeverType"
```

Added in v1.0.0

## NullC (interface)

**Signature**

```ts
export interface NullC extends NullType {}
```

Added in v1.5.3

## NullType (class)

**Signature**

```ts
export declare class NullType {
  constructor()
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "NullType"
```

Added in v1.0.0

## NumberC (interface)

**Signature**

```ts
export interface NumberC extends NumberType {}
```

Added in v1.5.3

## NumberType (class)

**Signature**

```ts
export declare class NumberType {
  constructor()
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "NumberType"
```

Added in v1.0.0

## OutputOfDictionary (type alias)

**Signature**

```ts
export type OutputOfDictionary<D extends Any, C extends Any> = { [K in OutputOf<D>]: OutputOf<C> }
```

Added in v1.0.0

## OutputOfPartialProps (type alias)

**Signature**

```ts
export type OutputOfPartialProps<P extends AnyProps> = { [K in keyof P]?: OutputOf<P[K]> }
```

Added in v1.0.0

## OutputOfProps (type alias)

**Signature**

```ts
export type OutputOfProps<P extends AnyProps> = { [K in keyof P]: OutputOf<P[K]> }
```

Added in v1.0.0

## PartialC (interface)

**Signature**

```ts
export interface PartialC<P extends Props>
  extends PartialType<P, { [K in keyof P]?: TypeOf<P[K]> }, { [K in keyof P]?: OutputOf<P[K]> }, unknown> {}
```

Added in v1.5.3

## PartialType (class)

**Signature**

```ts
export declare class PartialType<P, A, O, I> {
  constructor(
    name: string,
    is: PartialType<P, A, O, I>['is'],
    validate: PartialType<P, A, O, I>['validate'],
    encode: PartialType<P, A, O, I>['encode'],
    readonly props: P
  )
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "PartialType"
```

Added in v1.0.0

## Props (interface)

**Signature**

```ts
export interface Props {
  [key: string]: Mixed
}
```

Added in v1.0.0

## ReadonlyArrayC (interface)

**Signature**

```ts
export interface ReadonlyArrayC<C extends Mixed>
  extends ReadonlyArrayType<C, ReadonlyArray<TypeOf<C>>, ReadonlyArray<OutputOf<C>>, unknown> {}
```

Added in v1.5.3

## ReadonlyArrayType (class)

**Signature**

```ts
export declare class ReadonlyArrayType<C, A, O, I> {
  constructor(
    name: string,
    is: ReadonlyArrayType<C, A, O, I>['is'],
    validate: ReadonlyArrayType<C, A, O, I>['validate'],
    encode: ReadonlyArrayType<C, A, O, I>['encode'],
    readonly type: C
  )
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "ReadonlyArrayType"
```

Added in v1.0.0

## ReadonlyC (interface)

**Signature**

```ts
export interface ReadonlyC<C extends Mixed>
  extends ReadonlyType<C, Readonly<TypeOf<C>>, Readonly<OutputOf<C>>, unknown> {}
```

Added in v1.5.3

## ReadonlyType (class)

**Signature**

```ts
export declare class ReadonlyType<C, A, O, I> {
  constructor(
    name: string,
    is: ReadonlyType<C, A, O, I>['is'],
    validate: ReadonlyType<C, A, O, I>['validate'],
    encode: ReadonlyType<C, A, O, I>['encode'],
    readonly type: C
  )
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "ReadonlyType"
```

Added in v1.0.0

## RecordC (interface)

**Signature**

```ts
export interface RecordC<D extends Mixed, C extends Mixed>
  extends DictionaryType<D, C, { [K in TypeOf<D>]: TypeOf<C> }, { [K in OutputOf<D>]: OutputOf<C> }, unknown> {}
```

Added in v1.5.3

## RecursiveType (class)

**Signature**

```ts
export declare class RecursiveType<C, A, O, I> {
  constructor(
    name: string,
    is: RecursiveType<C, A, O, I>['is'],
    validate: RecursiveType<C, A, O, I>['validate'],
    encode: RecursiveType<C, A, O, I>['encode'],
    public runDefinition: () => C
  )
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "RecursiveType"
```

Added in v1.0.0

### type (property)

**Signature**

```ts
readonly type: C
```

Added in v1.0.0

## RefinementC (interface)

**Signature**

```ts
export interface RefinementC<C extends Any, B = TypeOf<C>> extends RefinementType<C, B, OutputOf<C>, InputOf<C>> {}
```

Added in v1.5.3

## RefinementType (class)

**Signature**

```ts
export declare class RefinementType<C, A, O, I> {
  constructor(
    name: string,
    is: RefinementType<C, A, O, I>['is'],
    validate: RefinementType<C, A, O, I>['validate'],
    encode: RefinementType<C, A, O, I>['encode'],
    readonly type: C,
    readonly predicate: Predicate<A>
  )
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "RefinementType"
```

Added in v1.0.0

## StringC (interface)

**Signature**

```ts
export interface StringC extends StringType {}
```

Added in v1.5.3

## StringType (class)

**Signature**

```ts
export declare class StringType {
  constructor()
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "StringType"
```

Added in v1.0.0

## TupleC (interface)

**Signature**

```ts
export interface TupleC<CS extends [Mixed, ...Array<Mixed>]>
  extends TupleType<
    CS,
    CS extends { length: 1 }
      ? [TypeOf<CS[0]>]
      : CS extends { length: 2 }
      ? [TypeOf<CS[0]>, TypeOf<CS[1]>]
      : CS extends { length: 3 }
      ? [TypeOf<CS[0]>, TypeOf<CS[1]>, TypeOf<CS[2]>]
      : CS extends { length: 4 }
      ? [TypeOf<CS[0]>, TypeOf<CS[1]>, TypeOf<CS[2]>, TypeOf<CS[3]>]
      : CS extends { length: 5 }
      ? [TypeOf<CS[0]>, TypeOf<CS[1]>, TypeOf<CS[2]>, TypeOf<CS[3]>, TypeOf<CS[4]>]
      : unknown,
    CS extends { length: 1 }
      ? [OutputOf<CS[0]>]
      : CS extends { length: 2 }
      ? [OutputOf<CS[0]>, OutputOf<CS[1]>]
      : CS extends { length: 3 }
      ? [OutputOf<CS[0]>, OutputOf<CS[1]>, OutputOf<CS[2]>]
      : CS extends { length: 4 }
      ? [OutputOf<CS[0]>, OutputOf<CS[1]>, OutputOf<CS[2]>, OutputOf<CS[3]>]
      : CS extends { length: 5 }
      ? [OutputOf<CS[0]>, OutputOf<CS[1]>, OutputOf<CS[2]>, OutputOf<CS[3]>, OutputOf<CS[4]>]
      : unknown,
    unknown
  > {}
```

Added in v1.5.3

## TupleType (class)

**Signature**

```ts
export declare class TupleType<CS, A, O, I> {
  constructor(
    name: string,
    is: TupleType<CS, A, O, I>['is'],
    validate: TupleType<CS, A, O, I>['validate'],
    encode: TupleType<CS, A, O, I>['encode'],
    readonly types: CS
  )
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "TupleType"
```

Added in v1.0.0

## TypeC (interface)

**Signature**

```ts
export interface TypeC<P extends Props>
  extends InterfaceType<P, { [K in keyof P]: TypeOf<P[K]> }, { [K in keyof P]: OutputOf<P[K]> }, unknown> {}
```

Added in v1.5.3

## TypeOfDictionary (type alias)

**Signature**

```ts
export type TypeOfDictionary<D extends Any, C extends Any> = { [K in TypeOf<D>]: TypeOf<C> }
```

Added in v1.0.0

## TypeOfPartialProps (type alias)

**Signature**

```ts
export type TypeOfPartialProps<P extends AnyProps> = { [K in keyof P]?: TypeOf<P[K]> }
```

Added in v1.0.0

## TypeOfProps (type alias)

**Signature**

```ts
export type TypeOfProps<P extends AnyProps> = { [K in keyof P]: TypeOf<P[K]> }
```

Added in v1.0.0

## UndefinedC (interface)

**Signature**

```ts
export interface UndefinedC extends UndefinedType {}
```

Added in v1.5.3

## UndefinedType (class)

**Signature**

```ts
export declare class UndefinedType {
  constructor()
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "UndefinedType"
```

Added in v1.0.0

## UnionC (interface)

**Signature**

```ts
export interface UnionC<CS extends [Mixed, Mixed, ...Array<Mixed>]>
  extends UnionType<CS, TypeOf<CS[number]>, OutputOf<CS[number]>, unknown> {}
```

Added in v1.5.3

## UnionType (class)

**Signature**

```ts
export declare class UnionType<CS, A, O, I> {
  constructor(
    name: string,
    is: UnionType<CS, A, O, I>['is'],
    validate: UnionType<CS, A, O, I>['validate'],
    encode: UnionType<CS, A, O, I>['encode'],
    readonly types: CS
  )
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "UnionType"
```

Added in v1.0.0

## UnknownArrayC (interface)

**Signature**

```ts
export interface UnknownArrayC extends AnyArrayType {}
```

Added in v1.5.3

## UnknownC (interface)

**Signature**

```ts
export interface UnknownC extends UnknownType {}
```

Added in v1.5.3

## UnknownRecordC (interface)

**Signature**

```ts
export interface UnknownRecordC extends AnyDictionaryType {}
```

Added in v1.5.3

## UnknownType (class)

**Signature**

```ts
export declare class UnknownType {
  constructor()
}
```

Added in v1.5.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "UnknownType"
```

Added in v1.0.0

## Validate (type alias)

**Signature**

```ts
export type Validate<I, A> = (i: I, context: Context) => Validation<A>
```

Added in v1.0.0

## VoidC (interface)

**Signature**

```ts
export interface VoidC extends VoidType {}
```

Added in v1.5.3

## VoidType (class)

**Signature**

```ts
export declare class VoidType {
  constructor()
}
```

Added in v1.2.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "VoidType"
```

Added in v1.0.0

## appendContext

**Signature**

```ts
export declare function appendContext(c: Context, key: string, decoder: Decoder<any, any>, actual?: unknown): Context
```

Added in v1.0.0

## getContextEntry

**Signature**

```ts
export declare function getContextEntry(key: string, decoder: Decoder<any, any>): ContextEntry
```

Added in v1.0.0

## getFunctionName

**Signature**

```ts
export declare function getFunctionName(f: Function): string
```

Added in v1.0.0

## identity

**Signature**

```ts
export declare const identity: <A>(a: A) => A
```

Added in v1.0.0

## ~~Compact~~ (type alias)

**Signature**

```ts
export type Compact<A> = { [K in keyof A]: A[K] }
```

Added in v1.4.2

## ~~Exact~~ (type alias)

**Signature**

```ts
export type Exact<T, X extends T> = T & {
  [K in ({ [K in keyof X]: K } & { [K in keyof T]: never } & { [key: string]: never })[keyof X]]?: never
}
```

Added in v1.1.0

## ~~ObjectC~~ (interface)

**Signature**

```ts
export interface ObjectC extends ObjectType {}
```

Added in v1.5.3

## ~~ObjectType~~ (class)

**Signature**

```ts
export declare class ObjectType {
  constructor()
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "ObjectType"
```

Added in v1.0.0

## ~~PropsOf~~ (type alias)

**Signature**

```ts
export type PropsOf<T extends { props: any }> = T['props']
```

Added in v1.0.0

## ~~StrictC~~ (interface)

**Signature**

```ts
export interface StrictC<P extends Props> // tslint:disable-next-line: deprecation
  extends StrictType<P, { [K in keyof P]: TypeOf<P[K]> }, { [K in keyof P]: OutputOf<P[K]> }, unknown> {}
```

Added in v1.5.3

## ~~StrictType~~ (class)

**Signature**

```ts
export declare class StrictType<P, A, O, I> {
  constructor(
    name: string,
    // tslint:disable-next-line: deprecation
    is: StrictType<P, A, O, I>['is'],
    // tslint:disable-next-line: deprecation
    validate: StrictType<P, A, O, I>['validate'],
    // tslint:disable-next-line: deprecation
    encode: StrictType<P, A, O, I>['encode'],
    readonly props: P
  )
}
```

Added in v1.0.0

### \_tag (property)

**Signature**

```ts
readonly _tag: "StrictType"
```

Added in v1.0.0

## ~~TaggedExact~~ (interface)

**Signature**

```ts
export interface TaggedExact<Tag extends string, A, O = A> extends ExactType<Tagged<Tag>, A, O> {}
```

Added in v1.3.0

## ~~TaggedIntersectionArgument~~ (type alias)

**Signature**

```ts
export type TaggedIntersectionArgument<Tag extends string> =
  // tslint:disable-next-line: deprecation
  | [Tagged<Tag>]
  // tslint:disable-next-line: deprecation
  | [Tagged<Tag>, Mixed]
  // tslint:disable-next-line: deprecation
  | [Mixed, Tagged<Tag>]
  // tslint:disable-next-line: deprecation
  | [Tagged<Tag>, Mixed, Mixed]
  // tslint:disable-next-line: deprecation
  | [Mixed, Tagged<Tag>, Mixed]
  // tslint:disable-next-line: deprecation
  | [Mixed, Mixed, Tagged<Tag>]
  // tslint:disable-next-line: deprecation
  | [Tagged<Tag>, Mixed, Mixed, Mixed]
  // tslint:disable-next-line: deprecation
  | [Mixed, Tagged<Tag>, Mixed, Mixed]
  // tslint:disable-next-line: deprecation
  | [Mixed, Mixed, Tagged<Tag>, Mixed]
  // tslint:disable-next-line: deprecation
  | [Mixed, Mixed, Mixed, Tagged<Tag>]
  // tslint:disable-next-line: deprecation
  | [Tagged<Tag>, Mixed, Mixed, Mixed, Mixed]
  // tslint:disable-next-line: deprecation
  | [Mixed, Tagged<Tag>, Mixed, Mixed, Mixed]
  // tslint:disable-next-line: deprecation
  | [Mixed, Mixed, Tagged<Tag>, Mixed, Mixed]
  // tslint:disable-next-line: deprecation
  | [Mixed, Mixed, Mixed, Tagged<Tag>, Mixed]
  // tslint:disable-next-line: deprecation
  | [Mixed, Mixed, Mixed, Mixed, Tagged<Tag>]
```

Added in v1.3.0

## ~~TaggedIntersection~~ (interface)

**Signature**

```ts
export interface TaggedIntersection<Tag extends string, A, O = A> // tslint:disable-next-line: deprecation
  extends IntersectionType<TaggedIntersectionArgument<Tag>, A, O> {}
```

Added in v1.3.0

## ~~TaggedProps~~ (type alias)

**Signature**

```ts
export type TaggedProps<Tag extends string> = { [K in Tag]: LiteralType<any> }
```

Added in v1.3.0

## ~~TaggedRefinement~~ (interface)

**Signature**

```ts
export interface TaggedRefinement<Tag extends string, A, O = A> extends RefinementType<Tagged<Tag>, A, O> {}
```

Added in v1.3.0

## ~~TaggedUnionC~~ (interface)

**Signature**

```ts
export interface TaggedUnionC<Tag extends string, CS extends [Mixed, Mixed, ...Array<Mixed>]> // tslint:disable-next-line: deprecation
  extends TaggedUnionType<Tag, CS, TypeOf<CS[number]>, OutputOf<CS[number]>, unknown> {}
```

Added in v1.5.3

## ~~TaggedUnionType~~ (class)

**Signature**

```ts
export declare class TaggedUnionType<Tag, CS, A, O, I> {
  constructor(
    name: string,
    // tslint:disable-next-line: deprecation
    is: TaggedUnionType<Tag, CS, A, O, I>['is'],
    // tslint:disable-next-line: deprecation
    validate: TaggedUnionType<Tag, CS, A, O, I>['validate'],
    // tslint:disable-next-line: deprecation
    encode: TaggedUnionType<Tag, CS, A, O, I>['encode'],
    codecs: CS,
    readonly tag: Tag
  )
}
```

Added in v1.3.0

## ~~TaggedUnion~~ (interface)

**Signature**

```ts
export interface TaggedUnion<Tag extends string, A, O = A> extends UnionType<Array<Tagged<Tag>>, A, O> {}
```

Added in v1.3.0

## ~~Tagged~~ (type alias)

**Signature**

```ts
export type Tagged<Tag extends string, A = any, O = A> =
  // tslint:disable-next-line: deprecation
  | InterfaceType<TaggedProps<Tag>, A, O>
  // tslint:disable-next-line: deprecation
  | StrictType<TaggedProps<Tag>, A, O>
  // tslint:disable-next-line: deprecation
  | TaggedRefinement<Tag, A, O>
  // tslint:disable-next-line: deprecation
  | TaggedUnion<Tag, A, O>
  // tslint:disable-next-line: deprecation
  | TaggedIntersection<Tag, A, O>
  // tslint:disable-next-line: deprecation
  | TaggedExact<Tag, A, O>
  | RecursiveType<any, A, O>
```

Added in v1.3.0

## ~~getDefaultContext~~

**Signature**

```ts
export declare const getDefaultContext: (decoder: Decoder<any, any>) => Context
```

Added in v1.0.0

## ~~getValidationError~~

**Signature**

```ts
export declare const getValidationError: (value: unknown, context: Context) => ValidationError
```

Added in v1.0.0

## ~~mixed~~ (type alias)

Use `unknown` instead.

**Signature**

```ts
export type mixed = unknown
```

Added in v1.0.0
