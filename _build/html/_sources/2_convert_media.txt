2. Convert Media
================

The convert media module is where the magic happens. There are a few steps you need to take before converting your file. The firust of which is to decide which feature need to be used for your specific conversion. We have build out some common conversion templates, but you can also create your own template with user-selected features. 

If you are confused about which features need to be used to complete a conversion, please visit our `Conversion Settings Guide <http://cinnafilm.com/support/tachyon-settings-guide/>`_ for more information. There is also further explaination of the specific features below.

.. note:: The `Conversion Settings Guide <http://cinnafilm.com/support/tachyon-settings-guide/>`_ is specifically for Tachyon Settings. 


Choose output template
----------------------

First, you need to choose an output template. Cinnafilm has provided some boiler plate outputs that are some of the most common conversions. 

Create your own template
------------------------

The user can also create their own template within Pixel Strings. Do do that...
tktktktk
tktktktk

Feature descriptions
--------------------

In creating your own template, you will have to choose your features from the list below:


**Allow Telecine Removal** - Tachyon will automatically analyze every scene for a pattern which can be removed. 5:4 ratio telecine, 4:1 progressive pattern, repeated frames or others will be automatically identified and removed, releasing the 23.976 (or 25p) essence from the patterns surrounding it.


**Increased Detection Sensitivity** - Luminance changes such as scene fades can affect the pattern matching abilities of Tachyon. The increased detection sensitivity reduces the window of frames required to identify a pattern as well as makes the analysis engine less susceptible to luminance variance.


**Adjust for Cartoon/Anime** - Cartoon and anime often have many repeated frames, which can trip up automatic pattern removal. The cartoon/anime setting takes into consideration repeated frames when generating the 23.976 essence from 29.97i material.


**Adjust for Excessive Noise** - When files are generated through tape transfer, there are often chroma issues which arise, creating a cyan/yellow/green/magenta crawl in certain areas of the video. This setting ensures the analysis of patterns is performed in grayscale, eliminating the effect of chroma issues when detecting patterns for removal.  Keep in mind this feature will not remove chroma noise.


**Residual Combing Removal** - Editors sometimes overlay progressive graphics on top of telecine material, or composite telecine material into a telecine matte without matching the telecine cadence. This feature identifies residual combing post telecine removal and eliminates it automatically. There is a 2-3 FPS performance penalty for using this feature, but it is much faster than rotoscoping (which is the only viable solution other than Residual Combing Removal.)


**Enable Motion Compensation** - This setting invokes the Tachyon Motion Compensation engine for creation of new frames. It is recommended to leave this in AUTO unless the advanced features are fully understood. Auto enables Tachyon to adjust the MC algorithms as necessary to accommodate different video essences. For example, within a 29.97i project there could be 3 video essences:  True 59.94 fields, 29.97 progressive frames, and 23.976 which has been telecined. While it will playback just fine on a broadcast monitor, there are 3 distinct video rates which must be addressed individually if changing to any other frame rate. The 59.94 fields will deinterlace to 59.94p  The 29.97p is already progressive, so it will remain as is. The 29.97i telecine will be inverse-telecine'd to 23.976. When in AUTO mode, Tachyon will adjust the Motion Compensation settings for each scene of 59.94p, 29.97p and 23.976 video essences automatically - and this is imperative to producing the best possible results.  


**Compensation Amount** - This setting determines the level of which the frame generation engine will trust the calculated motion vectors. Settings range from Low to Extra High.


**Block Size** - his setting determines the "size of chunks" of video that will be analyzed.  Small = 8x8 pixels.  Medium = 16x16.  Large = 32x32.  Extra Large = 64x64.  When in AUTO mode, Tachyon will adjust the block size based on input frame rate and input raster to achieve the best possible results.


**Fallback Blend Area** - Fallback is the portion of the frame where inconclusive Motion Compensation must give way to portions of original image. When inconclusive motion vectors are encountered (such as two objects moving towards each other and one passes in front of the other), then fallback is necessary to prevent artifacts. The size of the fallback blend area will determine how much from the nearest original neighboring frame will be used.


**Allow 2:2 Insertion (PSF)** - This setting is essential for maintaining the filmic look of 23.976, 24, and 25p sourced material.  Allow 2:2 will double the frames, and then place each of the doubled frames into the upper and lower field of a frame container respectively.  The images will always playback as progressive, and the filmic look will be preserved while playing back in an interlaced container.


**Allow 2:3 Insertion** - This is the standard 5:4 ratio, AA BB BC CD DD pattern, for achieving a 29.97i output from 23.976 input.


**Allow Adaptive Insertion** - Allow Adaptive will use a plethora of pattern insertions (Euro, 2:2, 2:3, etc) to achieve a frame rate conversion by repeating fields/frames rather than generating new frames from motion compensation data


**Allow Double Frames** - When going from 24p-48p, 25p-50p, 29.97p-59.94p or 30p-60p, rather than generating double the frames from motion compensation data and wrecking the filmic look of the lower frame rate, Tachyon will simply double the frames so they play back twice as long in the container.


**Allow 4:6 Insertion** - 4:6 insertion is used to repeat 23.976 frames to fit into a 59.94p container. This algorithm is analogous to 2:3 insertion for 29.97i, and in fact, if you were to deinterlace a 2:3 telecine 29.97i, you would achieve the 4:6 pattern.


**Advanced Settings** - When features are requested by clients and want a quick turnaround on feature availability, or Cinnafilm engineers have determined a feature will not be used enough to warrant a dedicated GUI control, a character string is created for the feature to be invoked via the Advanced Settings command line input.  See the Advanced Settings List for current features which are available.


Supported Input Media
---------------------
**Formats**

**Framerates**


Supported Output Media
----------------------
**Formats**
	* ProRes
	* DNXHD
**Framerates**
	* 23.98
	* 24
	* 25
	* 29.97
	* 30
	* 50
	* 59.94
	* 60

.. note:: Some codec and framerate combinations are unsupported. 

**Continue to next topic...** :doc:`3_deliver`