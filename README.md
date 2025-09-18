# What I Changed for the Lab

Hey! Here's everything I had to fix and add to meet the lab requirements.

## Files I Renamed

Had to rename these files to match what the lab wanted exactly:
- `user_class.php` → `customer_class.php`
- `user_controller.php` → `customer_controller.php` 
- `register_user_action.php` → `register_customer_action.php`

## Missing Form Fields I Added

The registration form was missing two required fields:
- **Country** input field
- **City** input field

Added them both to `register.php` with proper styling and validation.

## Role Values I Fixed

The radio buttons had the wrong values. Lab said:
- 1 = Administrator 
- 2 = Customer (should be default)

So I flipped them and changed "Restaurant Owner" to "Administrator" to be more generic.

## New Validation I Added

### JavaScript Validation (`register.js`)
Before it was pretty basic. I added:
- **Email format checking** with regex
- **Phone number validation** (10-15 digits)
- **Name validation** (letters and spaces only, 2-100 chars)
- **Country/City validation** (2-30 chars)
- **Field length validation** to match database limits
- **Email uniqueness check** - hits the server to see if email already exists

### New Email Check Feature
Created `check_email_action.php` that checks if an email is already taken before you even submit the form.

## Database Class Updates (`customer_class.php`)

- Renamed the class from `User` to `Customer`
- Added `country` and `city` properties
- Changed `createUser()` to `addCustomer()` method
- Added email uniqueness checking in the `addCustomer()` method
- Updated the SQL INSERT to include country and city fields

## Controller Updates (`customer_controller.php`)

- Renamed `register_user_ctr()` to `register_customer_ctr()`
- Added `$country` and `$city` parameters
- Updated to use the new Customer class instead of User class

## Action Script Updates (`register_customer_action.php`)

- Added code to grab `$_POST['country']` and `$_POST['city']`
- Updated the controller call to pass all the new parameters
- Better error message when email already exists

## Better User Experience

- Added loading spinner when submitting the form
- Better error messages that tell you exactly what's wrong
- Real-time email checking so you know right away if your email is taken
- Form validates everything before even trying to submit

## What This Fixes

Before these changes, the registration would fail because:
- Missing required database fields (country, city)
- Wrong role values 
- No email uniqueness validation
- Weak client-side validation

Now it's fully compliant with the lab requirements and Thank You for the Register Sample. It really helped A lot!
