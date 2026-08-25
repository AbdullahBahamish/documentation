.. _intercompany_clearing:

=====================
Intercompany Clearing
=====================

Working in a multi-company environment often involves transactions between your own entities. The :guilabel:`Intercompany Clearing` feature automates the creation of intercompany accounting entries.

When a payment is registered between two of your companies, Odoo instantly matches the open customer invoices and vendor bills across both entities. This eliminates the need for manual spreadsheet tracking and ensures that the intercompany accounts are always in balance.

Prerequisites
=============

To use this feature, your database must meet the following requirements:

* :guilabel:`Multi-company environment`: You must have at least two active companies configured in your database.

Configuration
=============

Before the system can automatically post intercompany entries, you must configure the default reciprocal accounts and journals for **every** participating company.

Go to :menuselection:`Accounting --> Configuration --> Settings`.

On :guilabel:`Default Accounts` section, scroll to the :guilabel:`Inter-Company Transactions` and ensure the feature is enabled.

Define the following fields for your currently active legal entity:

   -:guilabel:`Inter-Company Journal`: The dedicated journal used to log cross-entity transfers.
   -:guilabel:`Reciprocal Inter-Company Account`: The clearing account used to balance debits and credits between your entities.


Switch to your other company using the company switcher and **repeat the process**.

.. important::
   These settings must be populated in **all** involved entities. If reciprocal journals or accounts are missing in even one company, Odoo cannot generate the balancing entries automatically.

.. example::
   *Company A* provides services to *Company B*. *Company A* issues a customer invoice, and *Company B* records a vendor bill. When the invoice is paid via the Inter-Company Journal, Odoo automatically records the payment in both entities—crediting the Reciprocal Account in one and debiting it in the other—instantly reconciling the open documents.