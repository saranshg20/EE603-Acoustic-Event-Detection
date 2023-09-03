The provided zip file has N file pairs of melspectograms and eventrolls

i.e., (melspec_00001.npy, eventroll_00001.npy),(melspec_00002.npy, eventroll_00002.npy), ...

A melspectrogram file has a shape of (1, 512, 1000). It can be thought as an image having one channel, height=512 and width=1000.
An eventroll matrix file has a shape of (11, 1000). Which represents 11 (0 to 10) different arrays where each array represents that 
whether event is on for that timestamp or not for that event type. It has value 1 if event on and 0 for event off. 

For example, if eventroll[4, 50:250] = 1, then it means that the event type no 4 (here sound of a dog) starts at timestamp 50 and length of event is 250 - 50 = 200 timestamps. Note that for each event type, there can be multiple events of same type in an eventroll for some event.

You have to predict the events present in an spectrogram (not their timestamps).
An additional python script eventroll_to_multihot_vector.py is given to convert eventrolls in the desired format.

The files provided are numpy arrays which can be loaded using np.load("<filename>.npy", allow_pickle=True)

events_types = {
    0: 'Alarm_bell_ringing', 
    1: 'Blender', 
    2: 'Cat', 
    3: 'Dishes', 
    4: 'Dog',
    5: 'Electric_shaver_toothbrush', 
    6: 'Frying', 
    7: 'Running_water',
    8: 'Silence', 
    9: 'Speech', 
    10: 'Vacuum_cleaner'
}

