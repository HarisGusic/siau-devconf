========================
Razvoj programa dev-conf
========================

.. toctree::

Definirane funkcije
===================

Datoteka `main.cpp`
-------------------

.. doxygenfile:: main.cpp

Datoteka `file.h`
-----------------

Sadrži generičke operacije sa datotekama koje se koriste u projektu.

.. doxygenfile:: file.h

.. admonition:: Dodatno pojašnjenje
   :class: tip
   
   Funkcija ``write`` treba podatke uređaja iz parametra ``data`` upisati u
   datoteku sa putanjom ``out``, koristeći kao predložak datoteku sa putanjom
   ``in``.

   .. rubric:: Primjer korištenja:

   .. code-block:: c++

      Device data = jsonParseDevice("factory_device.json");
      write(data, "device.h.in", "device.h");

Datoteka `symbols.h.in`
-----------------------

Sadrži ``#define`` direktive čije vrijednosti zavise od instalacijskih
parametara. Na primjer, u ovoj datoteci je definiran simbol ``TEMPLATE_DIR``
koji sadrži putanju direktorija u kojem se nalaze predlošci JSON datoteka.
Vrijednost ovog simbola se postavlja kroz CMake korištenjem ``configure_file``.

.. include:: _build/files/symbols.h.in
   :code: c++
   
