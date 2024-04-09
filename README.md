import itertools

def truth_table(boolean_function):
    variables = sorted(set(boolean_function.replace('not', '').replace('and', '').replace('or', '').replace('(', '').replace(')', '').split()))
    num_variables = len(variables)
    table_header = ' | '.join(variables) + ' | ' + boolean_function
    table_separator = '-' * len(table_header)

    print(table_header)
    print(table_separator)

    for combination in itertools.product([False, True], repeat=num_variables):
        variable_dict = {variables[i]: combination[i] for i in range(num_variables)}
        boolean_value = eval(boolean_function, variable_dict)
        truth_values = ' | '.join(str(int(comb)) for comb in combination) + ' | ' + str(int(boolean_value))
        print(truth_values)

def canonical_forms(boolean_function):
    # Assuming boolean_function is in canonical form
    forms = boolean_function.split(' or ')
    for form in forms:
        print(form)

# Example usage:
boolean_function = "A or D and T"
truth_table(boolean_function)
canonical_forms(boolean_function)
<!---
FALIARIVONYIloFanasina/FALIARIVONYIloFanasina is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
