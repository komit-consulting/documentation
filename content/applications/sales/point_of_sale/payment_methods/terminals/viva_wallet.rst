===========
Viva Wallet
===========

Connecting a **Viva Wallet** :doc:`payment terminal <../terminals>`  allows you to offer a fluid
payment flow to your customers and ease the work of your cashiers.

.. note::
   Viva Wallet lets you turn your phone into a mobile card reader: `Tap On Phone
   <https://www.vivawallet.com/gb_en/blog-tap-on-phone-gb>`_.

Configuration
=============

Start by creating your Viva Wallet account on `Viva Wallet's website <https://www.vivawallet.com>`_.

Locate your Viva Wallet credentials
-----------------------------------

When configuring Viva Wallet in Point of Sale, you need to use specific credentials that are
available in your Viva Wallet account. These credentials include your :ref:`Merchant ID
<viva_wallet/id-key>`, :ref:`API key <viva_wallet/id-key>`, :ref:`POS APIs credentials
<viva_wallet/pos-apis>`, and :ref:`Terminal ID <viva_wallet/identifier>` number.

.. _viva_wallet/id-key:

Merchant ID and API key
~~~~~~~~~~~~~~~~~~~~~~~

Locate your `Merchant ID and API key following the Viva documentation
<https://developer.vivawallet.com/getting-started/find-your-account-credentials/merchant-id-and-api-key/>`_.
Then, save the keys and paste them into the Odoo :guilabel:`Merchant ID` and :guilabel:`API Key`
fields :ref:`when creating the payment method <viva_wallet/method-creation>`.

.. image:: viva_wallet/access-cred.png
   :alt: merchant ID and API key fields

.. note::
   These credentials are used for APIs that authenticate with Basic Auth.

.. _viva_wallet/pos-apis:

POS APIs credentials
~~~~~~~~~~~~~~~~~~~~

Locate and generate your `POS APIs credentials following the Viva documentation
<https://developer.vivawallet.com/getting-started/find-your-account-credentials/pos-apis-credentials/>`_.
Then, save the keys and paste them into the Odoo :guilabel:`Client secret` and :guilabel:`Client ID`
fields :ref:`when creating the payment method <viva_wallet/method-creation>`.

.. warning::
   These credentials are only displayed once. Ensure you keep a copy to secure them.

.. image:: viva_wallet/api-cred.png
   :alt: Client secret and client ID fields

.. note::
   These credentials are used for Android and iOS POS Activation requests, as well as the Cloud
   Terminal API.

.. _viva_wallet/identifier:

Terminal ID
~~~~~~~~~~~

Your terminal ID number is used to identify your terminal. To find it:

#. Go to your Viva Wallet account and select the relevant account.
#. Go to :menuselection:`Sales --> Physical payments --> Card terminals` in the navigation menu.

The terminal ID number is located under the :guilabel:`Terminal ID (TID)` column. Save it to paste
it into the :guilabel:`Terminal ID` field :ref:`when creating the payment method
<viva_wallet/method-creation>`.

.. image:: viva_wallet/terminal-id.png
   :alt: Viva terminal ID

.. _viva_wallet/method-creation:

Configure the payment method
----------------------------

Enable the payment terminal in the :guilabel:`Payment Terminals` section :ref:`of the application
settings <configuration/settings>`.

Then, go to :menuselection:`Point of Sale --> Configuration --> Payment Methods`, and click
:guilabel:`New` to :doc:`create the related payment method <../../payment_methods>`. Set the journal
type as :guilabel:`Bank` and select :guilabel:`Viva Wallet` in the :guilabel:`Use a Payment
Terminal` field.

Finally, fill in the mandatory fields with your

- :ref:`Merchant ID and API key <viva_wallet/ID-key>`
- :ref:`Client ID and Client secret <viva_wallet/pos-apis>`
- :ref:`Terminal ID <viva_wallet/identifier>`

.. image:: viva_wallet/create-method-viva-wallet.png
   :alt: payment method creation form
   :scale: 75%

Then, save the form and copy the generated webhook URL of the :guilabel:`Viva Wallet Webhook
Endpoint` field. This URL is necessary :ref:`when configuring the Webhook <viva_wallet/webhook>`.

.. note::
   Should the Viva Wallet payment method be missing in the application settings,
   :doc:`activate the POS Viva Wallet module <../../../../general/apps_modules>` to enable it.

.. _viva_wallet/webhook:

Configure the Webhook
---------------------

Webhooks allow you to receive real-time notifications whenever a transaction occurs within your Viva
Wallet account. Set them up for `payment transactions following the Viva documentation
<https://developer.vivawallet.com/webhooks-for-payments/transaction-payment-created/>`_.

.. seealso::
   - `Setting up webhooks <https://developer.viva.com/webhooks-for-payments/#setting-up-webhooks>`_

Link the payment method to a POS
--------------------------------

You can select the payment method in your POS settings once the payment method is created. To do so,
go to the :ref:`POS' settings <configuration/settings>`, click :guilabel:`Edit`, and add the payment
method under the :guilabel:`Payment methods` field of the :guilabel:`Payments` section.

Pay with a payment terminal
===========================

When processing a payment, select the related payment method. Check the amount and click on
:guilabel:`Send`. Once the payment is successful, the status changes to :guilabel:`Payment
Successful`.

.. note::
   - | In case of connection issues between Odoo and the payment terminal, force the payment by
       clicking on :guilabel:`Force Done`, which allows you to validate the order.
     | This option is only available after receiving an error message informing you that the
       connection failed.
   - To cancel the payment request, click :guilabel:`cancel`.
