
## Variable to discuss

# 2. Boolean Variable
    
    is_enabled: false
    

# 3. List Variable
    
    language:
      - python
      - java
      - perl
    
# 4. Dictionary Variable
    
    language_version:
      python: 0.5
      java: 0.25
      perl: 0.75
    

 # 5. Referencing nested variable
    
    
    fruit_basket:
      - name: John
        fruits:
          - apple
          - orange
      - name: Jane
        fruits:
          - banana
          - apple
          - orange
    

  # 6. Variable from the my-vars.yml
  
  
    vars_files:
        - my-vars.yml



# Task to declare

    - name: Boolean variable
      debug:
        msg: "Variable is true"
      when: is_enabled
      tags:
        - boolean_var

    - name: List variable - Print list of computer language
      debug:
        var: language
      tags:
        - list_var

    - name: List variable - Reference individual item in listd
      debug:
       var: language_version[0]
      tags:
        - individual_item 

    - name: Dictionary Variable - Accessing individual specific fields
      debug:
        var: language_version.python

    - name: Get the value of apple from the nested variable
      debug:
        var: fruit_prices[fruit_basket[0].fruits[0]]

# Jinja 2 filter on variables

    - name: Using Jinja 2 filters on variables
      debug:
        var: fruit_prices.keys() | list | map('upper') | list

# Accessing variable inside playbook from my-vars.yml
    - name: Get the value of variable from my-vars.yml
      debug:
        var: vars_from_my_vars_yml

# Defining and accessing the variable at RunTime
    - name: Get the value from run time
      debug:
        var: version

# Defining and accessing the variable at RunTime
    - name: Print the value of variable when var file is passed at run time
      debug:
        var: other_variable
 


## RUN Playbook

```
ansible-playbook --inventory inventory/hosts ansible-variables-playbook.yml

```

