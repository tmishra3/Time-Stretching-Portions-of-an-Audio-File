# Time Stretching Portions of an Audio File [Algorithmic Approach Only]

Think of a sample as a rubber-band that you want to pin to a musical time ruler. In Live, the
pins are called Warp Markers. A Warp Marker locks a specific point in the sample (in sample
time) to a specific place in a measure (in beat time). You can use any number of Warp
Markers to create an arbitrary mapping of the sample’s inherent rhythm to a musical meter.
Warp Markers are used to tell Live’s engine when and at which tempo a given piece of
material should be played. If you are curious, Warp Markers are described in detail in section
9.2.2 of Live’s Reference Manual. For the sake of this task, please assume the following
behavior:

● An audio clip contains a reference to a sample and a collection of Warp Markers.
● There is at least one Warp Marker in the clip.
● Between two Warp Markers, the tempo is constant.
● The tempo before the first Warp Marker is the same as the tempo after the first Warp
Marker.
● The tempo after the last Warp Marker is specified separately in the input.
● Beat time is measured in beats, sample time is measured in seconds, and tempo is
measured in beats per second.

## Input description

There are 4 kinds of lines in the input:
1. Warp Marker definition
2. Definition of the tempo after the last marker
3. Sample time to beat time conversion
4. Beat time to sample time conversion

At least one Warp Marker and the tempo after the last Warp Marker should be defined
before the first conversion; otherwise, these can appear in any order.
Each line consists of a keyword followed by numeric arguments. All numeric values are
entered as doubles without units. Warp Marker and tempo definitions affect only the
conversions that come later in the input.

marker <beat time> <sample time>
  
end_tempo <value>

  s2b <sample time>

  b2s <beat time>

## Output description

  For each of the s2b and b2s lines, the corresponding output time is printed without unit.
  
## Example

  Input
marker 0.0 0.0
  
marker 1.0 5.0

  end_tempo 10.0

  b2s 0.5

  s2b 6.0
  
Output

  2.5

  11.0

### As this is an explanation of my approach, for the sake of mathematical formatting, I've included the PDF file I submitted.

[Programming Assignment #1 - Tanmay Mishra.pdf](https://github.com/tmishra3/Time-Stretching-Portions-of-an-Audio-File/files/7622059/Programming.Assignment.1.-.Tanmay.Mishra.pdf)
