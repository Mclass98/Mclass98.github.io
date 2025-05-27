
```mermaid
sequenceDiagram
    actor Hacker
    participant hacker_control_center
    participant bots
    participant internet
    participant user_firewall
    participant user_pc

    hacker->>hacker_control_center: access bots
    hacker_control_center->>bots: launches attack
    bots->>internet: asks access
    internet->>bots: allows traffic
    bots->>user_firewall: flood requests

    alt may pass
        user_firewall-->bots: unsafe
    else may not pass
        user_pc->>user_firewall: safe
        alt may pass
            user_firewall-->bots: unsafe
        else may not pass
            user_pc-->user_firewall: denied
        end
    end

note over Hacker,hacker_control_center: A hacker uses access point<br/>to issue command to bots
note over bots,internet: 100s of bots are used to attack a target
note over user_firewall,user_pc: the firewall will fight off bots,<br/>but the bombardment will keep user from gaining access




