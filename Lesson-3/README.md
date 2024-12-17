
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
 


## RUN Playbook

```
ansible-playbook --inventory inventory/hosts ansible-variables-playbook.yml

```

