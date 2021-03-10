# Kitties Pallet Design - Assignment 5 (Exchange Feature)

This is a design document submitted for substrate developer academy assignment 5 (Kitties Pallet)

## Storage (decl_storage!)

    * kitties: double_map (owner: AccountId, kitty_index: u32 )  => Option<kitty>
    * prices: map kitty_index: u32   => option<u32>

## Events (decl_event!)

    * KittyTransferred(AccountId, AccountId, u128),
    * KittyPurchased(AccountId, AccountId, u128),
<!-- [from, to , price] -->

## Errors (decl_error!)

    * NotTheOwnerOfKitty,
    * LessPayment,
    * MorePayment,

## Calls (decl_module!)

    * fn purchase_kitty(origin, kitty_id: u32, tokens: u128)
<!-- Question: what is equalent of payable in substrate? and what token can we accept? -->
    * fn put_kitty_for_sale(origin, kitty_id: u32, price: u128)
