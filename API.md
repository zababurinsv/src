## Objects

<dl>
<dt><a href="#Pets">Pets</a> : <code>object</code></dt>
<dd><p>Operations for pets.</p>
</dd>
<dt><a href="#Supporters">Supporters</a> : <code>object</code></dt>
<dd><p>Operations for supporters.</p>
</dd>
</dl>

<a name="Pets"></a>

## Pets : <code>object</code>
Operations for pets.

**Kind**: global namespace  

* [Pets](#Pets) : <code>object</code>
    * [.register(options)](#Pets.register) ⇒ <code>object</code>
    * [.adopt(options)](#Pets.adopt) ⇒ <code>object</code>

<a name="Pets.register"></a>

### Pets.register(options) ⇒ <code>object</code>
Registers a new pet into the Pet Adoption Center.

**Kind**: static method of [<code>Pets</code>](#Pets)  
**Returns**: <code>object</code> - Details about the transaction.  

| Param | Type | Description |
| --- | --- | --- |
| options | <code>object</code> | Options object. |
| options.name | <code>string</code> | The name of the pet. |
| options.type | <code>string</code> | Is it a dog. |
| options.breed | <code>string</code> | Which breed of dog or cat is it? |
| options.dateOfBirth | <code>string</code> | Date of birth of the pet. |
| [options.neutered] | <code>boolean</code> | Whether the pet is neutered or not. |

<a name="Pets.adopt"></a>

### Pets.adopt(options) ⇒ <code>object</code>
Some lucky pet is getting adopted!

**Kind**: static method of [<code>Pets</code>](#Pets)  
**Returns**: <code>object</code> - Details about the transaction.  

| Param | Type | Description |
| --- | --- | --- |
| options | <code>object</code> | Options object. |
| options.pet | <code>object</code> | The pet being adopted. |
| options.supporter | <code>object</code> | The supported who adopts the pet. |

<a name="Supporters"></a>

## Supporters : <code>object</code>
Operations for supporters.

**Kind**: global namespace  
<a name="Supporters.enroll"></a>

### Supporters.enroll(options) ⇒ <code>object</code>
Enrolls a new supporter into our Pet Adoption Center database.

**Kind**: static method of [<code>Supporters</code>](#Supporters)  
**Returns**: <code>object</code> - Details about the transaction.  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| options | <code>object</code> |  | Options object. |
| options.firstName | <code>string</code> |  | Supporter's first name. |
| options.lastName | <code>string</code> |  | Supporter's last name. |
| options.dateOfBirth | <code>string</code> |  | Supporter's date of birth. |
| [options.paymentTier] | <code>string</code> | <code>&quot;BASIC&quot;</code> | How much is the supporter contributing every month? |

