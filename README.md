# norme

## Introduction:

This Document aims at providing a norme for a collective project. Especially
ft_transcendence (project a 42 programing school).

## Functions:

### names:

Function names should start with a verb that gives a neat insight on what the
function will do. Then have a meaningfull name.

example:
```
build_array_for_window();
compute_total_screen_size();
find_next_index_in_array();
calculate_elapsed_time_since_last_event();
```

### prepend a tag to function names for distinguishing parts of the project:
to be UPDATED:
example:
```
front_end_build_array_of_pixels_for_window();
back_end_build_array_for_user_portfolio();
```

## Variables:

### Explicit names:

Variables should always have an explicit and inambiguous name (so that the
code can be read naturally without refering to the comment section).

__Reasonables exceptions examples:__
- "i" for iterations on indexes.
- "str" for strings.
- ...

Example: you declare a variable that contains a value in a certain unit, always
attach the unit at the end;

````
int angle_in_degrees;
int angle_in_radians;
int degrees_in_celcius;
int degrees_in_fahrenheit;
````

### Constness:

Try to declare variables as const in the first intention, downgrade to non
const if required.

### Add intermediary variables for a cleaner code:

example:

````
	char *screen_representation = make_array_for_screen(window.get_width() *window.get_heigth());

	//OR

	const int number_of_pixels = width_in_pixel * height_in_pixel;
	const char *screen_representation = make_array_for_screen(number_of_pixels);
}
````

### Variables representing a collection of data:

Variables that represent either a linked list, an array, or so, must have a
name that is plural (ends with an 's') so that we can easily understand they
can contain more than one element.
example:
````
		int number;
		int numbers[] = {1, 2};
````
