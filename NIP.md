NIP-TBD
======

Stable Diffusion 
-------------

`draft` `optional` `author:pixelrouter`

The purpose of this NIP is to allow users to send prompts to special relay's which will generate an image, using stable diffusion, for a fee specified in satoshis, and which will return a public link to the image to the user via encrypted direct message (NIP-04),


## Event format
This NIP specifies the use of the `TBD` event type, having in `prompt` a stable diffusion image prompt, and a list of tags described below:

* `prompt` the stable diffusion prompt
* `negative-prompt` stable diffusion negative prompt as string,
* `steps` image generation steps as integer,
* `sampler` image generation sampler name as string,
* `cfg-scale` configuration scale as integer,
* `seed` seed as integer,
* `size` image size as string],
* `model-hash` model hash as string,
* `denoising-strength` denoising strength as string,
* `ENSD` ENSD as string,
* `version` version as string,
* `hires-upscale` Hires upscale as string,
* `hires-upscaler` Hires upscaler as string

```json
{
  "id": <32-bytes lowercase hex-encoded sha256 of the the serialized event data>,
  "pubkey": <32-bytes lowercase hex-encoded public key of the event creator>,
  "created_at": <unix timestamp in seconds>,
  "kind": TBD,
  "tags": [
	["negative-prompt",<stable diffusion negative prompt as string>],
	["steps",<image generation steps as integer>],
	["sampler",<image generation sampler name as string>],
	["cfg-scale",<configuration scale as integer>],
	["seed",<seed as integer>],
	["size",image size as string],
	["model-hash",<model hash as string>],
	["denoising-strength",<denoising strength as string>],
	["ENSD",<ENSD as string>],
	["version",<version as string>],
	["hires-upscale",<Hires upscale as string>],
	["hires-upscaler",<Hires upscaler as string>],
  ],
  "prompt": <stable diffusion prompt as string>,
  "sig": <64-bytes hex of the signature of the sha256 hash of the serialized event data, which is the same as the "id" field>
}
```

## Suggested use cases

* A relay can earn satoshis by rendering an image using stable diffusion