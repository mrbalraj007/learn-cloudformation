
# And Fuction
Fn::And:
  - Fn::And acts as an AND operator
  - Minimum number of condition is 2
  - Maximum number of condition is 10
  - Syntax: Fn::And: [condition]
  - Short syntax: !And [condition]
  Example:
  MyAndCondition: !And
    - !Equals ["sg-mysggroup", !Ref ASecurityGroup]
    - !Condition SomeOtherCondition

# Equals Fuction
Fn::Equals:
  - Returns true if the two values are equal else it will return false
  - Syntax: Fn::Equals: [value_1, value_2]
  - Short Syntax: !Equals [value_1, value_2]
  Example:
  UseProdCondition:
  !Equals [!Ref EnvironmentType, prod]

# If Fuction
Fn::If:
  - metadata attribute, update policy attribute, and property values in the Resources section and Outputs section
  - Syntax: Fn::If: [condition_name, value_if_true, value_if_false]
  - Short syntax: !If [condition_name, value_if_true, value_if_false]
  Example:
  SecurityGroups:
    - !If [CreateNewSecurityGroup, !Ref NewSecurityGroup, !Ref ExistingSecurityGroup]
  Example: ~ # The second example seems incomplete or malformed in the image.

# Not Fuction
Fn::Not:
  - Fn::Not acts as a NOT operator
  - Syntax: Fn::Not: [condition]
  - Short syntax: !Not [condition]
  Example:
  MyNotCondition:
  !Not [!Equals [!Ref EnvironmentType, prod]]


# Or Fuction
Fn::Or:
  - Fn::Or acts as an OR operator
  - Minimum number of condition is 2
  - Maximum number of condition is 10
  - Syntax: Fn::Or: [condition, ...]
  - Short syntax: !Or [condition, ...]
  
  Example:
  MyOrCondition:
  !Or [!Equals [sg-mysggroup, !Ref ASecurityGroup], Condition: SomeOtherCondition]
