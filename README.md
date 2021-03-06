# README

Shopsy is a single page web application inspired by Etsy. It was build with a Ruby on Rails backend and a React / Redux frontend.

## Features

### Responsive

  * @media queries utilized for a smooth mobile browsing experience. 

### Authentication

  * Frontend uses react-modal to render the session form.

  <img src="http://res.cloudinary.com/brainzilla/image/upload/v1506620686/shopsy-session-form_xdbnns.png" width="600"/>

  * Passwords are not stored in the databse as strings. Shopsy utilizes `BCrypt` to hash and salt the passwords for secure storage. 

  ```
  class User < ApplicationRecord
  #...

  def password=(password)
    @password = password
    self.password_digest = BCrypt::Password.create(password)
  end

  def is_password?(password)
    BCrypt::Password.new(self.password_digest).is_password?(password)
  end
```

### Product Listing

  * Users can easily navigate to products

  <img src="http://res.cloudinary.com/brainzilla/image/upload/v1506621314/shopsy-product-index-screenshot_kzluuv.png" width="600"/>


### Comments

  * Users can create, edit and delete comments on the product show page while logged in.

  <img src="http://res.cloudinary.com/brainzilla/image/upload/v1506621015/shopsy-comments-section-screenshot_r0vegu.png" width="600" />

### Search

  * Users can search products by name and description.

  <img src="http://res.cloudinary.com/brainzilla/image/upload/v1506621169/shopsy-search-screenshot_hhryrm.png" width="600" />

### Cart

  * Users can add and remove products.

  <img src="http://res.cloudinary.com/brainzilla/image/upload/v1506696337/shopsy-cart-screenshot_sw85p5.png" width="600" />

## Future Features

###  Categories

  * This will allow users to go directly to product category via the categories nav.

### Product creation

  * Users will be able to create and edit products via a user page.

### Enhanced product images

  * Product page will have detail images and a lightbox.
