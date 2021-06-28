# Norm ft_transcendence

## I) Brief:

This Document is providing a norm for the development of the project ft_transcendence. It gives the main guidelines we should all agree upon and follow when working together and using the same tools.

Following common guidelines should facilitate the communication between teammates and will hopefully maintain a high workflow over time.
It should help us in producing a code that is clearer for everyone.

TODO:
	create a separate file named style guide for the style of coding. It should
	 talk about things, like:
	 - use camelcase
	 - how many spaces for indentation (2 or 4)
	 - egyptian style for brackets?
	 - definition of functons after the function is actually needed in the code..

## Functions:

TODO:
**This document should be discussed and modified with the whole team before starting the project.**

## II) Checkpoints:
TODO
- how many meetings a weeks? when?
- set up/agree on small dealines when possible?
- trouver un plage horaire dans la journée où on se connecte tous ensemble.

## III) Tools / Resources:

TODO:
 create list, add links, and explain what they are here for.
__List of resources:__
- link on logigram.
- link on tools like asana.
- link on the project broken down in parts.

## IV) General Work Flow:

1. If starting a new project part, find a unit test framework suitable and set it up.
2. Use Asana, always update it. This allows all of us to have visibility on what is going on. This avoids duplicating work. And this maintains a higher productivity for the whole team in general.
3. If starting a new part that will interface with another part, make sure to discuss with the teammate on the other end. When you agree on the informations required, update the diagram that contains the interfaces, for everyone to see.
4. If starting a new feature, create a new git branch that will act like the "master" branch for this feature.

## V) Asana:
It is like a trello, but a bit more suited for a bigger team.
The different project parts should have their own boards (understand their own list of tasks).
__Example:__
_For one big project part, we will have one board, and we would have that big project part separated into features.
Each feature is a "batch" with a "batch name" found between brackets. Then each feature/batch needs a couple of functions to be coded._

> task 1: \[chat\]front_end__create_a_new_chat();
> 
> task 2: \[chat\]back_end__create_a_new_chat();
> 
> task 3: \[chat\]back_end__delete_a_chat();

Refer to the diagram that contains the main project parts for the batch names. Try to stay coherent.

### Creating Asana tasks:
When creating a new asana task, inspire yourself from the tasks already created, try to stay coherent.

* tasks should have a coherent name: \[general name of the batch\] + name of the specific function(). 

	__Examples:__
	
	- \[CRUD_new_user\]front_end__create_new_user();
	
	- \[CRUD_new_user\]front_end__read_existing_user();

*  Tasks should have an explanatory comment, sufficient so that anyone can pick up the task and work on it.

*  Tasks should have an internal todo list, with at least:
	- comment code
	- code function
	- test code

### Workflow with Asana:

1. You start a new asana task: add yourself on the task, so that we avoid duplicates.
2. You are done with a task: mark it as done on asana (The code must be clean).
3. You spot a new task: create a new asana task, even if you are already busy. So that anyone can pick it up.
4. You dont know what to do: pick up an asana task.
5. You really don't konw what to do: ... Request for a little meeting.

## VI) Interfacing parts:

TODO: create a diagram in which we update the interface of different project's parts.

Clearly define the interface between two project parts before coding them.
Once the interface is defined/agreed upon, it should be added into the diagram that shows inerfaces.

An interface is like a communication protocol. It is an agreement so that two entities can communicate with each other without ambiguities.

__Example:__

```
//part A: collects all the data for a new client.
//part B: will add a new client in the database.

typedef struct s_new_client_for_db
{
	char *first_name;
	char *last_name;
	int max_name_length = 255;
	char *e_mail;
	char *encrypted_password;
}		t_new_client_for_db;

//part A's OUTPUT is formated like part B's INPUT:

//part A should have a prototype like:
t_new_client_for_db parse_new_client_from_web_form();

//part B should have a prototype like:
void	insert_new_client_in_database(t_new_client_for_db new_client);
```

## VII) Unit testing:

Basic functionalities should be unit tested in an automated and reproductible way.
We want the test to be run automatically when we try to git push on the remote server.

__Prerequisites:__
- Functions should do only one thing. (really short functions)
- Functions that have dependencies, should use Dependency injection as much as possible (https://stackoverflow.com/questions/130794/what-is-dependency-injection). 
- Before starting to code a project part, research and setup a suitable unit test framework, so that the next person just needs to immitate and insert more code.

__Aims:__
- test with 80/90% coverage of the code (100% is not reasonable).
- test the dumbest things, like initialised variables...

## VIII) Git:

### Unit tests when pushing
If a push attempts fails the tests, the push should be rejected by the remote git server.

### naming branches:
TODO

### merging with master:
TODO

## IX) Code:

TODO:
- agree on a norme for addoption or rejection of camelcase.

### General:
The code will be written **once** and read **many times**. So the code should be written **FOR** the reader.

It must be **clear** and **self-explanatory**.

Think about the ratio _WTF/minute_ when someone reads your code for the first time. Try to keep this ratio as low as possible.

### Comments:
Comment your code, dont necessarily lose time making comments on things that ar0e already self-explanatory in the code.
But comment your code:
- Why the function exists? or What it does?
- The inputs and what they represent?
- what are the different returned values?
- Exceptions raised? their types?
- a little drawing in the comment if really necessary...

Comment your code.

### Comment your code.

## X) Functions:

### Name starts by a verb:

Function names should start with a verb that gives a neat insight on what the
function will do. Then have a complete and meaningfull name that follows that verb.

__Examples:__
```
build_array_for_window();
compute_total_screen_size();
find_next_index_in_array();
calculate_elapsed_time_since_last_event();
```

### Tags for projects parts:

In order to easily distinguish parts of the project, we should agree on a precise hierarchy of tags to be prepended to the function names.

TODO:
- agree on usage of tags for project parts, yes or no?
- if yes agree on the project parts and the hierarchy between them.
- integrate the RESTFUL vocabulary in our naming convention?
- integrate the CRUD (Creat, Read, Update, Delete) vocabulary in our naming convention?
- more ideas?

__Examples:__
```
back_end__build_array_for_user_portfolio();
front_end__authentication__update_password();
front_end__cart__clear_items_in_cart();
front_end__payment__redirect_to_customers_bank_page();

back_end__database__read_password_for_user();
be__db__read_password_for_user();

back_end__database__delete_customer();

fe__auth__set_password_for_new_user();
```

## XI) VARIABLES:

### Explicit names:

Variables must have an explicit and inambiguous name (so that the
code can be read naturally without refering to the comments section).

__Example 1:__

```
int width;

//Versus

int width_of_comment_section;
```

__Example 2:__

_You declare a variable that contains a value in a certain unit, then make the effort to
attach the unit at the end._

````
int time_in_ms;
int time_in_sec;

int angle_in_degrees;
int angle_in_radians;
````

__Reasonable exceptions:__
* "i" for iterations on indexes.
* "str" for strings.
* etc...

### Constness:

Try to declare variables as "const" in the first intention, downgrade to "non
const" if required.

<<<<<<< HEAD
### Constants:

When a variable is a constant and its value is hardcoded (known before "compile
time"), give it a capital name.

### Add intermediary variables for a cleaner code:
=======
### Cleaner code:
>>>>>>> 227132b2c9b3403c01bbae0db5b4d04818e95e18

Declare intermediary variables for the sake of readability.

__Example:__

```
char *screen_representation = build_array_for_screen(window.get_width() *window.get_heigth());

	//Versus

const int number_of_pixels = window.get_width() * window.get_height();
const char *screen_representation = build_array_for_screen(number_of_pixels);
```

### Names for arrays and so:

Variables that represent an array or a linked-list or ... (understand "any collection of data") must have a
name that is plural (ends with an 's').
It shows they can contain more than one element, that we can iterate on them.

__Example:__

```
	int number;
	int numbers[] = {1, 2};
```

## XII) TODOS:

In the code, when you are making temporary modifications, add a `//TODO comment`, in case you forget...

If you create a code that works but that is unfinished, add a `//TODO comment`, in case you forget...

`//TODO` comments can be found easily and can be fixed later or at the end of the project.

## XIII) Optimisations:
Don't try to optimize a code that you havent benchmarked, and that will end up in a framework you havent coded, and that will be transpiled in a language you dont know...

Its a school project, lets prioritize readability and produce a quick but neat project.
