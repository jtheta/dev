# jtheta.internal.design

**NOTE: this document is a work in progress. If you have suggestions, comments, etc, please [submit an issue](https://github.com/jtheta/faq/issues) or a [pull request](https://github.com/jtheta/faq/issues).**

## Problem Statement

Integrating machine learning into existing applications is not an easy task. By some estimations, it requires an entirely new team to develop these features. It also requires the collaboration of the business, researchers, developers, and design.

Several tools and frameworks have been developed to offset these costs, but only solve one piece of the puzzle.

Deciding what tools to use, and which practices to follow prevents teams from being productive. A bulletproof platform is needed in order for teams to integrate these new features into their applications.

## Personas

| Name | Title | Languages / Tools | Description |
|------|-------|--------|-------------|
| Jill | Enterprise Developer | angular, C#, Java, sh | large app dev
| Vince | Startup Developer | react, node.js, go | agile dev
| Lacey | Researcher | r, python | proves ideas
| Gail | Mathematician | matlab, r, excel  | designs / improves models
| Drew | Professor | matlab, r, powerpoint  | teacher
| Jean | Student | matlab, java, c++  | university student
| Bryan | Ops | sh, groovy, python, docker, jenkins | sets up infra, keeps things running


## Design Plan

### Pain Points

| Pain Point | Who |
|------------|-----|
| Its very tedious and time consuming to clean data | Jill, Vince, Lacey
| This is an example of a *pain point*. It should include quotes and links. | Jill, Vince
| This is another pain point! | Drew, Jean

### Problems We Solve


#### Cleaning Data (Jill, Vince, Lacey, Drew)

> Cleaning Data is hard. Raw data is never perfect. When you are working with tons of data,
> its hard to spot all the cases where the data is wrong, mal-formated / corrupted, missing,
> in the wrong format, inconsistent, etc.
>
> Unstructured data (eg. audio, images) has other challenges, compression, cropping, aligning,
> and other tasks related to preparing for use by a model that expects consistency.
>
> Machines like vectors and matrices of normalized 32 bit integers. Its not always practical
> to create these "clean" machine ready versions of raw data.

#### Gathering Data (Jill, Vince, Lacey, Drew)

> Structured data exists in many places. Databases of all sorts, eg. MySQL, DB2, etc, and
> files of all kinds, eg. `.csv`, `.xls`.
>
> Unstructured data can come in many formats of audio, video and images.
>
> Machines expect this data in a consistent format, a NxN dimensional matrix of 32 bit integers.
> This means aggregating data (join, sum, sort, etc), filtering it. Then converting the gathered
> values into a matrix expected by the model/machine.

#### Normalization  (Jill, Vince, Lacey, Drew)

> Once data is gathered and cleaned, it must be turned into input features, commonly called `x`
> and depending on the use case (eg. typical supervised learning), a set of labels for these
> examples, `y`.
>
> This step also includes normalizing data.

#### Neural Diagnosis  (Gail, Drew, Jean)

> Determining if a certain model is working or not is tough. It is very important  that it is
> practical to diagnose these sorts of issues. Being able to visualize the precision, recall, 
> cost, accuracy, etc of a model, as its trained, is not an easy problem to solve.

#### Training Resources

> Training a model that uses large amounts of data will take tremendous resources. This is similar to rendering high resolution computer graphics for movies. The difference is that frames in a movie can easily be split amongst workers in a cluster. Where as in ML, the entire set of
examples and labels must be available to a single executor of the cost function J.

#### App Integration

> TBD

#### Live Data

> Same problems above, but the data is not persisted somewhere. Eg. self driving car learns as it drives. Voice recognition learns as you speak.

#### Production Resources

> TBD

#### Reproductivity

> "Works on my machine" but not in production.

### Solutions

TBD

### Prototype

TBD

### Test

TBD

<!-- Notes:

Scaling Best Practices:

 - Resource Consumption (Time, CPU, Mem, etc)
  - Stochastic Gradient Descent
  - Mini-Batch Gradient Descent
  - Map Reduce (for n > 1 local/dist. cores)
  - Neural Specific Hardware
 - Code / People
  - Machine Learning Pipelines
    - eg. pass an image through a sequence of components
    - 1 team per pipeline component
    - Mocking
     - Giving perfect results from prev stages in the pipeline
     - Isolate a single component
  - Sliding windows classifier
 - Model Performance
  - Most Reliable: Low Bias trained on a Massive Training Set
   - Verify this by plotting Learning Curves!
  - Artificial Training Data Syntheses
   - eg. generating ex of diff fonts for OCR
   - Distort / Warp
   - Amplify
   - Increase difficulty
   - Adding noise
   - "How can we get 10x as much data?"
    - Collect / label it yourself
    - Crowd source 
   - Ceiling Analysis
    - Where to allocate resources?
     - What component / stage needs improving
  - Tips
   - Most val resource is time of eng working on the system!!!
   - Worst thing: work on something that doesn't improve performance of model
   - Single Real Number Evaluation Metric
    - Accuracy or f1, etc
   - Dont trust your "gut feeling"
    - "I think I should work on this component!"
    - Analysis is a better way to decide where to put focus
  
    
Problem Statement Outline:

  - Who
   - Enterprise Development Teams
   - Startup Development Teams
   - Academics
   - Researchers
   - Mathematicians
   - UI Developers
   - Backend Developers
   - IT / Operations
   - Google, Amazon, Apple
  - What
   - Building Machine Learning Models for Use in Applications
   - Integrating into existing applications
   - Using existing/legacy data, services, infrastructure etc
  - Where
   - Enterprise
   - Startup
   - Universities
   - Research Labs
  - When
   - For the past 5 or 6 years, companies such as Google, Apple, Amazon, etc, have been researcching and deve
  - Why
   - Tasks that could never before be given to machines, now can
   - Machines are cheaper, faster, and scale more efficiently

-->