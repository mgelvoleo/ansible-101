
## Variable to discuss

# 1. String Variable
    main_playbook_variable: "foo"


# 2. Boolean Variable
    
    is_enabled: false
    

# 3. List Variable
    
    fruits:
      - apple
      - banana
      - orange
    
# 4. Dictionary Variable
    
    fruit_prices:
      apple: 0.5
      banana: 0.25
      orange: 0.75
    

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
    

 



# Task to declare to a task 


    - name: String Variable from - main_playbook_variable
      debug:
        var: main_playbook_variable 

    - name: Boolean variable
      debug:
        msg: "Variable is true"
      when: is_enabled
     

    - name: List variable - Print list of computer language
      debug:
        var: language
     

    - name: List variable - Reference individual item in list
      debug:
       var: language_version[0]
     
    - name: Dictionary Variable - Accessing individual specific fields
      debug:
        var: language_version.python

    - name: Get the value of apple from the nested variable
      debug:
        var: fruit_prices[fruit_basket[0].fruits[0]]

    - name: Dictionary Variable - Accessing all dictionary variable
      debug:
        var: fruit_prices





## RUN Playbook

```
ansible-playbook --inventory inventory/hosts ansible-variables-playbook.yml

```

