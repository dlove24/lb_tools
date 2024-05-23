---
title: Troubleshoot
nav_order: 1
---

# Troubleshooting

# Goals

Solutions don't usually work first time, and this How To covers the core checks you should take to identify corrective actions. More detailed discussions are in the [Further Reading](/howto/trouble/index.html#further-reading) section. The checklists below based on material written by Tony Kuphaldt in his _Troubleshooting_ chapter from _Lessons in Electric Circuits, Reference, Volume 5_.

## Further Reading

* [Troubleshooting. _Lessons in Electric Circuits_, Reference, Volume 5.](/media/pdf/LEC_TBL.pdf)

## Questions to Ask Before Proceeding

When facing a problem, first ask the following questions. The answer to these will guide you to the checklist of possible further questions and actions

- [ ] _Complete the [_Triage Checklist_ checklist](#triage-checklist) to isolate the failure_{: .green}.

If the system, sub-system or component is still not functioning correctly, go through the following. Here 'system' refers to the isolated section identified through the [_Triage Checklist_ checklist](#triage-checklist) above

- [ ] _Has the system ever worked before_{: .green}? If **no** go to the [_Likely Failures in Unproven Systems_ checklist](#likely-failures-in-unproven-systems).
- [ ] _Has this system proven itself to be prone to certain types of failure_{: .green}? If **yes**, go to the [_Prior Occurrence_ checklist](#prior-occurrence).
- [ ] _Is the failure sudden, or unexpected_{: .green}? _Is data available for the previous behaviour of the system_{: .green}? If **yes** to either question, go to the [_Likely Failures in Proven Systems_ checklist](#likely-failures-in-proven-systems).

If the above does not isolate the problem, complete the following and restart with the [_Triage Checklist_ checklist](#triage-checklist)

- [ ] [_Final checks_ checklist](#final-checks)

## Triage Checklist

**Isolate the system or sub-system causing the failure**

- [ ] _Swap identical components_{: .green}. In a system with identical or parallel subsystems, swap components between those subsystems and see if your problem moves with the swapped component. If it does, you've just swapped the faulty component. Replace the component and check the items in the [_Prior Occurrence_ checklist](#prior-occurrence).

- [ ] _Remove parallel components_{: .green}. Where a system contains parallel or redundant components, start removing these components (one at a time) and see if things start to work again.

- [ ] _Divide system into sections and test those sections_{: .green}. Check the inputs and outputs of each sub-system, measuring the signals going into or out of each sub-system. Verify your measurements against simulation, theory, or prior tests to identify the faulty sub-system.

- [ ] _Simplify and rebuild_{: .green}. Strip down to a small, working section or system. Then rebuild gradually to isolate the part of the system where the failure is evident.

- [ ] _Measures and trap a signals_{: .green}. Set up instrumentation (such as a oscilloscope, data-logger, or multimeter set on "record" mode) to monitor a signal over a period of time. This is especially helpful when tracking down intermittent problems, which have a way of showing up the moment you've turned your back and walked away.

## Prior Occurrence

**Check historic failure modes first**

- [ ] _Check for recent alterations_{: .green}. Check that your changes have not altered the historic behaviour of the system. Re-run historic tests to verify the expected outputs have not changed.

- [ ] _Identify correct functionality_{: .green}. Look for what the system _is_ doing correctly; in other words, identify where the problem is _not_, and focus your efforts elsewhere. Components or subsystems necessary for the parts that are giving a correct result are probably okay. The degree of fault can often tell you what part of it is to blame.

- [ ] _Hypothesize_{: .green}. Check hypotheses, based on your knowledge of how a system works. Check for failures, starting with the most likely based on circumstances, history, or knowledge of component weaknesses.


## Likely Failures in Proven Systems

**Check the following, in the order listed. Make sure you have completed the [_Triage checklist_](#triage-checklist) first**.


 - [ ] _Operator error_{: .green}. Check procedures, instructions, and other directions _fully_ to ensure you are following them correctly.

- [ ] _Bad wire connections_{: .green}. Check connection points in plug-and-socket connectors, terminal strip, or splices using a multimeter in continuity mode. Make sure _all_ wire and components are fully inserted into breadboards and other temporary circuits. Check mechanical switch contacts, ensuring they work correctly. Check termination of wires, to ensure a proper electrical: especially for stranded wires.

- [ ] _Check for ground faults_{: .green}. Visually, and with a multimeter, check that all wires, outputs and conductors are correctly grounded. With a multimeter, check metal casings, paths and connections for faults which are (temporarily) giving you a short circuit.

- [ ] _Power supply problems_{: .green}. Use a multimeter or oscilloscope to check the inputs voltage and current is correct. In the case of AC power, check the expected frequency and phase matches the system requirements. Use a multimeter to check that fuses and other disconnecting components are working correctly. 

- [ ] _Active components_{: .green}. Check that your static handling procedures are correct, and that the you have no damaged components though improper handling. Check datasheets for diagrams, tables and graphs of expected behaviour, and then verify your components against these, to check components have not aged or failed.

- [ ]  _Passive components_{: .green}. Use an LCR bridge or multimeter to check the component value, and functionality. Check the following, in the following order of likely failure 

  - Capacitors (shorted), especially _electrolytic_ capacitors. The paste electrolyte tends to lose moisture with age, leading to failure. Over-voltage transients puncture thin dielectric layers.
  - Diodes open (rectifying diodes) or shorted (Zener diodes).
  - Inductor and transformer windings open or shorted to conductive core. You can often detect insulation breakdown failures related to overheating (insulation breakdown) by smell.
  - Resistors open, seldom shorted. Usually this is due to over-current heating, although it is less frequently caused by over-voltage transient (arc-over) or physical damage (vibration or impact). Resistors may also change resistance value if overheated!

## Likely Failures in Unproven Systems

**Check the following, in the order listed. Make sure you have completed the [_Triage checklist_](#triage-checklist) first**.

- [ ] _Wiring problems_{: .green}. Check for assembly errors, such as connection to the wrong point or poor connector fabrication. Double-check breadboard connections against the circuit diagram.
  
- [ ] _Power supply problems_{: .green}. Use a multimeter or oscilloscope to check the inputs voltage and current is correct. In the case of AC power, check the expected frequency and phase matches the system requirements. Use a multimeter to check that fuses and other disconnecting components are working correctly. Check that the circuit load is not larger than expected, resulting in overloading and subsequent failure of power supplies.

- [ ] _Defective components_{: .green}. Check _all_ components --- active or passive --- against expected values and behaviour. Check components against datasheets, especially that your pin connections are correct _for the component you are testing_ (not all 'identical' components have the same pin layout). Check datasheets for diagrams, tables and graphs of expected behaviour, and then verify your components against these.  

- [ ] _Improper system configuration_{: .green}. Check the inputs and output of microcontrollers and microprocessors, using a multimeter or oscilloscope. Look for voltage and timing mismatches, signal propagation delays, PWM outputs and other improper behaviour from the program code. Check the tolerance of components for power ratings, impedance mismatches, and other limits. Check that components with configuration "jumpers" or switches are "programmed" to give the expected behaviour. Check that you have calibrated sensors, instruments, and controlling mechanisms, and that the calibration procedures are correct.

- [ ] _Design error_{: .green}. Check the fundamental theory of operation for your circuit, and that this solution is appropriate. Ideally, cross-check this design against theory, using simulations to identify possible issues and problems. Check the outputs of the simulation and theory match the output of the system you are testing. 

## Final Checks

**When all else fails, make sure you have discussed and discounted the following items. Then return to the [_Triage checklist_](#triage-checklist) when you have finished, and repeat the troubleshooting checklists**.

- [ ] _Don't assume brand-new components will always be good_{: .green}. While it is often true that a new component will be in good condition, it is not _always_ true. It is also possible that a component has been mis-labelled and may have the wrong value (usually this mis-labeling is a mistake made at the point of distribution or warehousing and not at the manufacturer, but again, _not always_!).

- [ ] _Not periodically checking your test equipment_{: .green}. This is especially true with battery-powered instruments, as weak batteries may give spurious readings. When using instruments to safety-check for dangerous voltage, remember to test the meter on a known source of voltage both _before_ and _after_ checking the circuit, to make sure the meter is in proper operating condition.

- [ ] _Assuming there is only one failure to account for the problem_{: .green}.Single-failure system problems are ideal for troubleshooting, but sometimes failures come in multiple numbers. In some instances, the failure of one component may lead to a system condition that damages other components. Sometimes a component in marginal condition goes undetected for a long time, then when another component fails the system shows problems with _both_ components.

- [ ] _Mistaking coincidence for causality_{: .green}. Just because two events occurred at almost the same time does _not_ necessarily mean one event _caused_ the other! They may be both consequences of a common cause, or they may be totally unrelated! If possible, try to duplicate the same condition suspected to be the cause and see if the event suspected to be the coincidence happens again. If not, then there is either no causal relationship as assumed. This may mean there is no causal relationship between the two events whatsoever, or that there is a causal relationship, but just not the one you expected.

- [ ] _Self-induced blindness_{: .green}. After a long effort at troubleshooting a difficult problem, you may become tired and begin to overlook crucial clues to the problem. Take a break and let someone else look at it for a while. Having time to (unconsciously) think though a problem can make an amazing difference. On the other hand, it is usually a bad idea to solicit help at the start of the troubleshooting process. Effective troubleshooting involves complex, multi-level thinking, which is hard to communicate with others. More often than not, "team troubleshooting" takes more time and causes more frustration than doing it yourself. An exception to this rule is when the knowledge of the troubleshooters is complementary: for example, a technician who knows electronics but not machine operation, teamed with an operator who knows machine function but not electronics.

- [ ] _Failing to question the troubleshooting work of others on the same job_{: .green}. This may sound rather cynical and misanthropic, but it is sound scientific practice. Because it is common to overlook 'insignificant' details, troubleshooting data received from another troubleshooter should be personally verified before proceeding. This is a common situation when troubleshooters "change shifts" and a technician takes over for another technician who is leaving before troubleshooting completes. It is important to exchange information, but do not assume the prior technician checked everything they said they did, or checked it against specifications.
