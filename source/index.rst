.. tips documentation master file, created by
   sphinx-quickstart on Wed May 24 15:28:10 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to tips's documentation!
================================

Contents:

.. toctree::
   :maxdepth: 2

   contents/GIT-issues
   contents/Diagram
   contents/Convention
   contents/Testing
   contents/IDE



Indices and tables
==================

* :ref:`diagrams-example-ref`
* :ref:`table-example-ref`
* :ref:`code-block-example-ref`
* :ref:`diagram-with-markdown-series-ref`
* :ref:`references-ref`

..  _diagrams-example-ref:

I. Diagram example
-------------------

.. image:: _static/diagram-clinic-create.png

.. hidden-code-block:: python
    :label: --- View Clinic create diagram source ---

    sequenceDiagram
    User->> View: Gestures (Click on [Create new] link)
    View->> ClinicsController: preview()①+
    ClinicsController->> +ClinicCreate: Data Validation②+
    Note right of ClinicCreate: Model Validate
    loop Data Validation
      ClinicCreate->>ClinicCreate: __construct()
    end
    ClinicCreate-->> -ClinicsController: Response from Validation
    View->> ClinicsController: create()③+
    ClinicsController->> +ClinicComponent: clinicInsert()④+
    ClinicComponent-->> -ClinicsController: $clinicObject
    ClinicsController-->> View: $result
    View-->> User: New view to User

------------------------------

..  _table-example-ref:

II. Table example
-----------------

      ======= ======================================
      No      Description
      ======= ======================================
      [No.11] [No] column
      [No.12] [Name] column
      [No.13] [Owner] column
      [No.14] [Register Date] column
      [No.15] [Phone] column
      [No.16] [Edit] link
      [No.17] [Delete] link
      [No.18] The pagination for search result
      [No.21] [Action] column
      ======= ======================================

..  _code-block-example-ref:

III. Code block example
------------------------

#. Finding all clinics exist in database with condition inputed at [Clinic] screen

    * File: Clinics/ClinicsController.php
    * Function: search()

    .. code-block:: php

        <?php
        ...
        /**
         * Function to get search result
         * @access public
         * @return array
         */
        public function search()
        {
          if (!$this->request->is('post')) {
            $this->redirect(array('action' => 'index'));
          }
          $errorMsg = null;
          $result   = array();
          $params   = $this->request->data['clinic'];
          $this->ClinicSearch->set($params);
          if ($this->ClinicSearch->validates()) {
            $result = $this->Clinic->get($params, $this->_searchFields);
          } else {
            $errorMsg = $this->ClinicSearch->validationErrors;
            $this->set('validateError', $errorMsg);
          }
          $this->set(compact('result'));
        }
        ...

..  _diagram-with-markdown-series-ref:

IV. Diagrams with Markdown series
----------------------------------

* 1. Draw Diagrams With Markdown

    * Sequence, Flowchart, GanttChart
        * http://support.typora.io/Draw-Diagrams-With-Markdown

    * Typora download
        * https://typora.io

    * Creating diagrams in Sphinx
        * http://build-me-the-docs-please.readthedocs.io/en/latest/Using_Sphinx/UsingGraphicsAndDiagramsInSphinx.html

* 2. Mermaid Library Detail

    * Github: https://github.com/knsv/mermaid
    * Mermaid docs
        * http://knsv.github.io/mermaid
    * sample editor (do not use in project because security risk)
        * http://knsv.github.io/mermaid/live_editor/
    * Sphinx extension
        * https://github.com/mgaitan/sphinxcontrib-mermaid

* 3. js-sequence-diagrams (Turns text into UML sequence diagrams)

    * https://bramp.github.io/js-sequence-diagrams/
        * https://github.com/bramp/js-sequence-diagrams/blob/master/README.md

* 4. Reference more skill with Markdown

    * http://support.typora.io/

* 5. Markdown Cheatsheet

    * https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#code
    * https://help.github.com/categories/writing-on-github/

* 6. Live Markdown Editor (Do not use in project because security risk, just practice)

    * https://jbt.github.io/markdown-editor

* 7. Read more

    * 6 JS Libraries for Building Visualized Charts & Graphs
        * http://codecondo.com/6-js-libraries-building-visualized-charts-graphs/
    * draw.io
        * https://github.com/jgraph/draw.io

..  _references-ref:

V. References
--------------

* Sơn-san tips
