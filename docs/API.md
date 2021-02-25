## Objects

<dl>
<dt><a href="#Pets">Pets</a> : <code>object</code></dt>
<dd><p>Operations for pets.</p>
</dd>
<dt><a href="#Supporters">Supporters</a> : <code>object</code></dt>
<dd><p>Operations for supporters.</p>
</dd>
<dt><a href="#Transactions">Transactions</a> : <code>object</code></dt>
<dd><p>Transaction types.</p>
</dd>
</dl>

<a name="Pets"></a>

## Pets : <code>object</code>
Operations for pets.

**Kind**: global namespace  

* [Pets](#Pets) : <code>object</code>
    * [.register(pet)](#Pets.register)
    * [.adopt(options)](#Pets.adopt) ⇒ [<code>TransactionResponse</code>](#Transactions.TransactionResponse)
    * [.Pet](#Pets.Pet) : <code>object</code>
    * [.PetTypes](#Pets.PetTypes) : <code>object</code>
    * [.PetBreeds](#Pets.PetBreeds) : <code>object</code>

<a name="Pets.register"></a>

### Pets.register(pet)
Registers a new pet into the Pet Adoption Center.

**Kind**: static method of [<code>Pets</code>](#Pets)  

| Param | Type | Description |
| --- | --- | --- |
| pet | [<code>Pet</code>](#Pets.Pet) | The pet. |

**Example**  
```js
const sdk = require('pet-adoption-center');

const transaction = sdk.pets.register({
    name: 'Atticus',
    type: sdk.PET_TYPES.DOG,
    breed: sdk.DOG_BREEDS.FRENCH_BULLDOG,
    dateOfBirth: '2010-03-10',
    neutered: false
});
```
<a name="Pets.adopt"></a>

### Pets.adopt(options) ⇒ [<code>TransactionResponse</code>](#Transactions.TransactionResponse)
Some lucky pet is getting adopted!

**Kind**: static method of [<code>Pets</code>](#Pets)  
**Returns**: [<code>TransactionResponse</code>](#Transactions.TransactionResponse) - Details about the transaction.  

| Param | Type | Description |
| --- | --- | --- |
| options | <code>object</code> | Options object. |
| options.pet | [<code>Pet</code>](#Pets.Pet) | The pet being adopted. |
| options.supporter | [<code>Supporter</code>](#Supporters.Supporter) | The supported who adopts the pet. |

**Example**  
```js
const sdk = require('pet-adoption-center');

// Register a pet
const registerTx = await sdk.pets.register({
    name: 'Atticus',
    type: sdk.PET_TYPES.DOG,
    breed: sdk.DOG_BREEDS.FRENCH_BULLDOG,
    dateOfBirth: '2010-03-10',
    neutered: false
});

// Enroll a supporter
const enrollTx = await sdk.supporters.enroll({
    name: 'Atticus',
    type: sdk.PET_TYPES.DOG,
    breed: sdk.DOG_BREEDS.FRENCH_BULLDOG,
    dateOfBirth: '2010-03-10',
    neutered: false
});

// It's a match!
const adoptTx = sdk.pets.adopt({ pet: registerTx.data, supporter: enrollTx.data });
```
<a name="Pets.Pet"></a>

### Pets.Pet : <code>object</code>
**Kind**: static typedef of [<code>Pets</code>](#Pets)  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| name | <code>string</code> | The name of the pet. |
| type | [<code>PetTypes</code>](#Pets.PetTypes) | Is it a dog? |
| breed | [<code>PetBreeds</code>](#Pets.PetBreeds) | Which breed of dog or cat is it? |
| dateOfBirth | <code>string</code> | Date of birth of the pet. |
| [neutered] | <code>boolean</code> | Whether the pet is neutered or not. |

<a name="Pets.PetTypes"></a>

### Pets.PetTypes : <code>object</code>
**Kind**: static typedef of [<code>Pets</code>](#Pets)  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| DOG | <code>string</code> | A dog. |
| CAT | <code>string</code> | A cat. |

<a name="Pets.PetBreeds"></a>

### Pets.PetBreeds : <code>object</code>
**Kind**: static typedef of [<code>Pets</code>](#Pets)  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| FRENCH_BULLDOG | <code>string</code> | A funny looking frenchie. |
| KOMONDOR | <code>string</code> | A dog with a beautiful hairdo. |

<a name="Supporters"></a>

## Supporters : <code>object</code>
Operations for supporters.

**Kind**: global namespace  

* [Supporters](#Supporters) : <code>object</code>
    * [.enroll(supporter)](#Supporters.enroll) ⇒ [<code>TransactionResponse</code>](#Transactions.TransactionResponse)
    * [.Supporter](#Supporters.Supporter) : <code>object</code>
    * [.PaymentTiers](#Supporters.PaymentTiers) : <code>object</code>

<a name="Supporters.enroll"></a>

### Supporters.enroll(supporter) ⇒ [<code>TransactionResponse</code>](#Transactions.TransactionResponse)
Enrolls a new supporter into our Pet Adoption Center database.

**Kind**: static method of [<code>Supporters</code>](#Supporters)  
**Returns**: [<code>TransactionResponse</code>](#Transactions.TransactionResponse) - Details about the transaction.  

| Param | Type | Description |
| --- | --- | --- |
| supporter | [<code>Supporter</code>](#Supporters.Supporter) | The supporter. |

**Example**  
```js
const sdk = require('pet-adoption-center');

const transaction = sdk.supporters.enroll({
    firstName: 'Atticus',
    lastName: sdk.PET_TYPES.DOG,
    dateOfBirth: '1983-01-01'
});
```
<a name="Supporters.Supporter"></a>

### Supporters.Supporter : <code>object</code>
**Kind**: static typedef of [<code>Supporters</code>](#Supporters)  
**Properties**

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| firstName | <code>string</code> |  | Supporter's first name. |
| lastName | <code>string</code> |  | Supporter's last name. |
| dateOfBirth | <code>string</code> |  | Supporter's date of birth. |
| [paymentTier] | [<code>PaymentTiers</code>](#Supporters.PaymentTiers) | <code>BASIC</code> | How much is the supporter contributing every month? |

<a name="Supporters.PaymentTiers"></a>

### Supporters.PaymentTiers : <code>object</code>
**Kind**: static typedef of [<code>Supporters</code>](#Supporters)  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| BASIC | <code>number</code> | Basic payment tier. |
| GOLD | <code>number</code> | Gold payment tier. |

<a name="Transactions"></a>

## Transactions : <code>object</code>
Transaction types.

**Kind**: global namespace  
<a name="Transactions.TransactionResponse"></a>

### Transactions.TransactionResponse : <code>object</code>
**Kind**: static typedef of [<code>Transactions</code>](#Transactions)  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| success | <code>boolean</code> | Whether the transaction was successful or not. |
| transactionId | <code>string</code> | Unique identifier of the transaction. |
| data | [<code>Pet</code>](#Pets.Pet) \| [<code>Supporter</code>](#Supporters.Supporter) | Whatever entity was created in this transaction. |

